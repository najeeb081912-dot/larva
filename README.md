hello thithis is my stock trader ai frontend heres a good compose to get started
services:
  larva:
    image: waffle12/larva:latest
    container_name: larva
    restart: unless-stopped
    ports:
      - "56391:8000"   # API Port
      - "57391:8000"   # frontend
    volumes:
      - ./docs:/app/documents
      - ./chroma:/app/chroma
      - ./models:/app/models
      - ./data:/app/data
    environment:
      - FINNHUB_API_KEY=
      - GROQ_API_KEY=
      - LLM_MODEL=qwen/qwen3.8-27b
      - SIGNUP_CODE=hello

My app allows for you into import data and have the ai read it. It is very intuitive. It also has a basic paper trader with few big stocks I hope to expand this app to make it more usable for the masses.
