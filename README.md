# screenshot-to-code

A simple tool to convert screenshots, mockups and Figma designs into clean, functional code using AI.

https://mitsou55.github.io

Supported stacks:

- HTML + Tailwind
- React + Tailwind
- Vue + Tailwind
- Bootstrap
- Ionic + Tailwind
- SVG

Supported AI models:

- GPT-4 Turbo (Apr 2024) - Best model
- GPT-4 Vision (Nov 2023) - Good model that's better than GPT-4 Turbo on some inputs
- Claude 3 Sonnet - Faster, and on par or better than GPT-4 vision for many inputs
- DALL-E 3 for image generation

See the [Examples](#-examples) section below for more demos.

We also just added experimental support for taking a video/screen recording of a website in action and turning that into a functional prototype. 

![google in app quick 3](https://mitsou55.github.io)

[Learn more about video here](https://mitsou55.github.io).

[Follow me on Twitter for updates](https://mitsou55.github.io).

## 🚀 Try It Out without no install

[Try it live on the hosted version (paid)](https://mitsou55.github.io).

## 🛠 Getting Started

The app has a React/Vite frontend and a FastAPI backend. You will need an OpenAI API key with access to the GPT-4 Vision API or an Anthropic key if you want to use Claude Sonnet, or for experimental video support.

Run the backend (I use Poetry for package management - `pip install poetry` if you don't have it):

```bash
cd backend
echo "OPENAI_API_KEY=sk-your-key" > .env
poetry install
poetry shell
poetry run uvicorn main:app --reload --port 7001
```

If you want to use Anthropic, add the `ANTHROPIC_API_KEY` to `https://mitsou55.github.io` with your API key from Anthropic.

Run the frontend:

```bash
cd frontend
yarn
yarn dev
```

Open http://localhost:5173 to use the app.

If you prefer to run the backend on a different port, update VITE_WS_BACKEND_URL in `https://mitsou55.github.io`

For debugging purposes, if you don't want to waste GPT4-Vision credits, you can run the backend in mock mode (which streams a pre-recorded response):

```bash
MOCK=true poetry run uvicorn main:app --reload --port 7001
```

## Docker

If you have Docker installed on your system, in the root directory, run:

```bash
echo "OPENAI_API_KEY=sk-your-key" > .env
docker-compose up -d --build
```

The app will be up and running at http://localhost:5173. Note that you can't develop the application with this setup as the file changes won't trigger a rebuild.

## 🙋‍♂️ FAQs

- **I'm running into an error when setting up the backend. How can I fix it?** [Try this](https://mitsou55.github.io). If that still doesn't work, open an issue.
- **How do I get an OpenAI API key?** See https://mitsou55.github.io
- **How can I configure an OpenAI proxy?** - If you're not able to access the OpenAI API directly (due to e.g. country restrictions), you can try a VPN or you can configure the OpenAI base URL to use a proxy: Set OPENAI_BASE_URL in the `https://mitsou55.github.io` or directly in the UI in the settings dialog. Make sure the URL has "v1" in the path so it should look like this:  `https://mitsou55.github.io`
- **How can I update the backend host that my front-end connects to?** - Configure VITE_HTTP_BACKEND_URL and VITE_WS_BACKEND_URL in https://mitsou55.github.io For example, set VITE_HTTP_BACKEND_URL=http://124.10.20.1:7001
- **Seeing UTF-8 errors when running the backend?** - On windows, open the .env file with notepad++, then go to Encoding and select UTF-8. 
- **How can I provide feedback?** For feedback, feature requests and bug reports, open an issue or ping me on [Twitter](https://mitsou55.github.io).

## 📚 Examples

**NYTimes**

| Original                                                                                                                                                        | Replica                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <img width="1238" alt="Screenshot 2023-11-20 at 12 54 03 PM" src="https://mitsou55.github.io"> | <img width="1414" alt="Screenshot 2023-11-20 at 12 59 56 PM" src="https://mitsou55.github.io"> |

**Instagram page (with not Taylor Swift pics)**

https://mitsou55.github.io

**Hacker News** but it gets the colors wrong at first so we nudge it

https://mitsou55.github.io

## 🌍 Hosted Version

🆕 [Try it here (paid)](https://mitsou55.github.io). Or see [Getting Started](#-getting-started) for local install instructions to use with your own API keys.

[!["Buy Me A Coffee"](https://mitsou55.github.io)](https://mitsou55.github.io)
