# VoxelChat

A polished, static AI chat and image-generation interface designed for **GitHub Pages**. It discovers model catalogs from OpenAI-compatible providers, including OpenRouter's hundreds of available models, and sends requests directly from your browser.

## Deploy on GitHub Pages

1. In the repository, open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select `main` and the `/(root)` folder, then save.
4. Open the published Pages URL after the deployment finishes.

The site is plain HTML, CSS, and JavaScript—no Node server or build step is required. GitHub Pages serves the root `index.html`; `server.js` is not used by the static app.

## Connect chat models

1. Open **Settings & providers** inside VoxelChat.
2. Choose **OpenRouter — hundreds of models**, enter an OpenRouter API key, and save.
3. Use the model selector in the message composer. VoxelChat fetches the provider's live model list; available models depend on your account and provider.

OpenAI, custom OpenAI-compatible APIs, and local Ollama are also supported. For Ollama, allow the Pages origin in Ollama's `OLLAMA_ORIGINS` configuration and make the local server reachable from the browser. A hosted GitHub Pages site cannot reach another user's localhost unless they configure that local service and browser access.

## Image generation

Open **Image studio** and configure an image API base URL, image model, and API key in Settings. The current implementation sends OpenAI-compatible `POST /images/generations` requests (for example, OpenAI's Images API). A chat provider's key is reused when the image key is blank. The endpoint must allow browser CORS requests and support the requested image model and parameters.

## Important security and hosting limits

GitHub Pages is static hosting; it cannot securely store API keys or hide provider requests behind a server. Keys are saved in this browser's local storage and sent directly to the chosen provider. Use a restricted key, avoid shared devices, and never commit keys to this repository. For a public production app, put provider calls behind a backend you control, with authentication, rate limiting, and secret management.

Chat history and settings are stored in the browser's local storage. Clearing site data removes them. Model availability, pricing, and image-generation support are determined by the selected provider.
