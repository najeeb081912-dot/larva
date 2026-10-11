
# Larva — Stock Trading AI

Hello! This is my stock trading AI application. Larva lets you import data for an AI to analyze, and it includes a basic paper trader with several major stocks.

## Features

- Import your own data for AI analysis
- AI-powered data analysis
- Basic paper trading with major stocks
- Persistent storage for documents, models, and application data

## Getting Started

Create a `compose.yaml` file with the following configuration:

```yaml
services:
  larva:
    image: waffle12/larva:latest
    container_name: larva
    restart: unless-stopped
    ports:
      - "56391:8000"
      - "57391:8000"
    volumes:
      - ./docs:/app/documents
      - ./chroma:/app/chroma
      - ./models:/app/models
      - ./data:/app/data
    environment:
      FINNHUB_API_KEY: ""
      GROQ_API_KEY: ""
      LLM_MODEL: "qwen/qwen3.8-27b"
      SIGNUP_CODE: "hello"
```

### Configuration

| Variable | Purpose |
|---|---|
| `FINNHUB_API_KEY` | API key for Finnhub market data |
| `GROQ_API_KEY` | API key for Groq-hosted AI models |
| `LLM_MODEL` | AI model to use |
| `SIGNUP_CODE` | Code required for registration, if enforced by the app |

Add your API keys before starting the application.

Run it with:

```bash
docker compose up -d
```

## About

My goal is to expand Larva into a more capable and user-friendly stock trading simulator. Contributions, suggestions, and feedback are welcome!
