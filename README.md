# 🔮 Dify + Crazyrouter Setup Guide

> Connect Dify platform to 300+ AI models via Crazyrouter — Save 45% on API costs.

[Crazyrouter](https://crazyrouter.com?ref=github) — One API key, all major AI models, 45% cheaper.

## 💰 Price Comparison

| Model | Official (In/Out per 1M tokens) | Crazyrouter | Savings |
|-------|--------------------------------|-------------|---------|
| Claude Opus 4 | $15 / $75 | $8.25 / $41.25 | **45%** |
| Claude Sonnet 4 | $3 / $15 | $1.65 / $8.25 | **45%** |
| GPT-4o | $2.50 / $10 | $1.38 / $5.50 | **45%** |
| Gemini 2.5 Pro | $1.25 / $10 | $0.69 / $5.50 | **45%** |

## ⚡ Setup Steps

### 1. Get Crazyrouter API Key
Sign up at [crazyrouter.com](https://crazyrouter.com?ref=github) and create an API key.

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

#### Method B: Docker Environment Variables
```bash
docker run -d \
  -p 80:80 \
  -e OPENAI_API_KEY=sk-your-crazyrouter-key \
  -e OPENAI_API_BASE=https://crazyrouter.com/v1 \
  langgenius/dify-web
```

### 3. Add Multiple Models
Repeat Step 2 for each model you want to use:
- `claude-opus-4-20250514`
- `claude-sonnet-4-20250514`
- `gpt-4o`
- `gpt-4o-mini`
- `gemini-2.5-pro`

All through the same Crazyrouter API key!

## 🎯 Recommended Model Setup for Dify

| Dify Feature | Recommended Model | Why |
|-------------|-------------------|-----|
| Chat Assistant | `claude-sonnet-4` | Best conversational quality |
| Workflow Agent | `claude-opus-4` | Complex reasoning tasks |
| Text Generation | `gpt-4o` | Fast and reliable |
| Embedding | `text-embedding-3-small` | Cost-effective embeddings |
| Quick Tasks | `gpt-4o-mini` | Cheapest option |

## 🔧 Dify Workflow Example

Build a RAG (Retrieval-Augmented Generation) pipeline:

1. **Knowledge Base** → Upload your documents
2. **Retrieval Node** → Search relevant chunks
3. **LLM Node** → Use `claude-sonnet-4` via Crazyrouter
4. **Output** → Return generated answer

All LLM calls go through Crazyrouter at 45% off.

## ❓ FAQ

**Q: Does Dify work with Crazyrouter?**
A: Yes, fully compatible via OpenAI-compatible API format.

**Q: Can I use Claude in Dify through Crazyrouter?**
A: Yes! Add Claude models as OpenAI-compatible providers with Crazyrouter base URL.

**Q: Does function calling / tool use work?**
A: Yes, all advanced features work through Crazyrouter.

**Q: Can I use different models in different workflow nodes?**
A: Yes, each node can use a different model, all through one Crazyrouter key.

## 🔗 Links
- 🌐 [Crazyrouter](https://crazyrouter.com?ref=github)
- 🔮 [Dify](https://github.com/langgenius/dify)
- 💬 [Telegram Community](https://t.me/crzrouter)
- 🐦 [Twitter @metaviiii](https://twitter.com/metaviiii)

## 📄 License
MIT

