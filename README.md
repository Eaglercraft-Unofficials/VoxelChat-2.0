# VoxelChat Local

A local-first AI chat app that connects to Ollama on your machine.

## Features
- Local-only chat experience
- Connects to any Ollama model you install locally
- Simple, responsive browser UI
- No external API key required

## Quick start

1. Install Ollama: https://ollama.com/
2. Pull a model:
   ```bash
   ollama pull llama3.2
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Start the app:
   ```bash
   npm start
   ```
5. Open http://localhost:3000

## Environment variables

```bash
PORT=3000
OLLAMA_BASE_URL=http://localhost:11434
DEFAULT_MODEL=llama3.2
```

## Project structure

- `server.js` — Express server and Ollama proxy
- `public/index.html` — chat interface
- `public/styles.css` — styling
- `public/app.js` — client-side behavior

## Notes

This app does not bundle a model. It expects Ollama to be installed and running locally.
