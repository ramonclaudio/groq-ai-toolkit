# Groq AI Toolkit

> **Unmaintained.** Use [`groq`](https://github.com/groq/groq-python), Groq's official Python SDK.

I've always preferred pair programming with LLMs from the terminal over copy-pasting from browser chats. Web UIs hit rate limits, lose context across tabs, and break flow when I'm moving code back and forth. When Groq opened their API in March 2024, the speed was the pitch: 800 tokens/sec on an LPU is a different kind of tool when you're streaming into a terminal. I wanted chat/text modes, streaming, JSON mode, system prompts, and sensible defaults behind a single CLI and Python entry. So I built this for myself.

Python wrapper and CLI for Groq's LPU inference API.

## Install

```bash
git clone https://github.com/ramonclaudio/groq-ai-toolkit.git
cd groq-ai-toolkit
pip install -r requirements.txt
```

## Configuration

Get an API key at https://console.groq.com/. Set via env var, `.env`, or pass directly:

```bash
export GROQ_API_KEY=your_api_key
```

## CLI

```bash
# Chat mode
python cli.py --chat

# Text mode
python cli.py --text --prompt "Explain the importance of low latency LLMs."
```

Type `exit` or `quit` to leave chat.

## Python

```python
from groq import Chat
Chat().run()

from groq import Text
Text().run(prompt="Explain the importance of low latency LLMs.")
```

## Options

| Description | CLI | Python |
| --- | --- | --- |
| Chat mode | `--chat` | `Chat()` |
| Text mode | `--text` | `Text()` |
| Prompt | `--prompt` | `prompt=` |
| API key | `--api_key` | `api_key=` |
| Model | `--model` | `model=` |
| System prompt | `--system_prompt` | `system_prompt=` |
| Streaming | `--stream` | `stream=True` |
| JSON mode | `--json` | `json=True` |
| Temperature | `--temperature` | `temperature=` |
| Max tokens | `--max_tokens` | `max_tokens=` |
| Top-p | `--top_p` | `top_p=` |
| Seed | `--seed` | `seed=` |
| Stop sequence | `--stop` | `stop=` |

## Models

| Model | Max tokens |
| --- | --- |
| `llama-3.1-70b-versatile` | 131072 |
| `llama-3.1-8b-instant` | 131072 |
| `llava-v1.5-7b-4096-preview` | 4096 |
| `llama-guard-3-8b` | 8192 |
| `llama3-70b-8192` | 8192 |
| `llama3-8b-8192` | 8192 |
| `llama2-70b-4096` | 4096 |
| `mixtral-8x7b-32768` | 32768 |
| `gemma-7b-it` | 8192 |
| `gemma2-9b-it` | 8192 |

## License

MIT
