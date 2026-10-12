# 🔮 Dify + Crazyrouter Setup Guide

> Connect Dify platform to available AI models via Crazyrouter.

[Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community) — One API key, all major AI models, .

## Current prices

[Current model prices](https://crazyrouter.com/en/pricing). Rates depend on the model, account group and billing unit; there is no universal discount. Check input, output, cache and task charges before use.

## ⚡ Setup Steps

### 1. Get Crazyrouter API Key
Sign up at [crazyrouter.com](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community) and create an API key.

### 2. Configure in Dify

#### Method A: Through Dify UI
1. Go to **Settings** → **Model Provider**
2. Click **Add Model Provider**
3. Select **OpenAI-API-compatible**
4. Fill in:
   - **Model Name**: `gpt-4o` (or any model you want)
   - **API Key**: `sk-your-crazyrouter-key`
   - **API Base URL**: `https://crazyrouter.com/v1`
5. Click **Save**

#### Self-hosted Dify

Deploy the complete stack using [Dify’s official Docker Compose guide](https://docs.dify.ai/en/self-host/quick-start/docker-compose). A standalone `dify-web` container is not a working Dify backend. Configure the provider through the model-provider UI.

### 3. Add Multiple Models
Repeat Step 2 for each model you want to use:
- `claude-opus-4-8`
- `claude-sonnet-4-6`
- `gpt-4o`
- `gpt-4o-mini`
- `gemini-2.5-pro`

All through the same Crazyrouter API key!

## 🎯 Recommended Model Setup for Dify

| Dify Feature | Recommended Model | Why |
|-------------|-------------------|-----|
| Chat Assistant | `claude-sonnet-4-6` | Best conversational quality |
| Workflow Agent | `claude-opus-4-6` | Complex reasoning tasks |
| Text Generation | `gpt-4o` | Fast and reliable |
| Embedding | `text-embedding-3-small` | Cost-effective embeddings |
| Quick Tasks | `gpt-4o-mini` | Cheapest option |

## 🔧 Dify Workflow Example

Build a RAG (Retrieval-Augmented Generation) pipeline:

1. **Knowledge Base** → Upload your documents
2. **Retrieval Node** → Search relevant chunks
3. **LLM Node** → Use `claude-sonnet-4-6` via Crazyrouter
4. **Output** → Return generated answer

All LLM calls go through Crazyrouter.

## ❓ FAQ

**Q: Does Dify work with Crazyrouter?**
A: Yes, fully compatible via OpenAI-compatible API format.

**Q: Can I use Claude in Dify through Crazyrouter?**
A: Yes! Add Claude models as OpenAI-compatible providers with Crazyrouter base URL.

**Q: Does function calling / tool use work?**
A: Tool calling and structured output depend on the selected model, Dify plugin and endpoint. Verify them with a small workflow first.

**Q: Can I use different models in different workflow nodes?**
A: Yes, each node can use a different model, all through one Crazyrouter key.

## 🔗 Links
- 🌐 [Crazyrouter](https://crazyrouter.com?utm_source=github&utm_medium=github&utm_campaign=dev_community)
- 🔮 [Dify](https://github.com/langgenius/dify)
- 💬 [Telegram Community](https://t.me/crzrouter)
- 🐦 [Twitter @metaviiii](https://twitter.com/metaviiii)

## 📄 License
MIT
