FROM python:3.10-slim

WORKDIR /app

# Install build dependencies required for compiling certain python packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Install Python requirements first to leverage Docker layer caching
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your application code and frontend files
COPY . .

# Create required internal application directories for databases, embeddings, and docs
RUN mkdir -p /app/data /app/documents /app/chroma /app/models

# Expose the FastAPI port
EXPOSE 8000

# Set environment variables to keep container logs unbuffered
ENV PYTHONUNBUFFERED=1

# Run the FastAPI server via uvicorn on port 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
