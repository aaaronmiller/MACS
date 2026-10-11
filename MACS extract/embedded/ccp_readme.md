# Claude Code Proxy (CCP) README
**Source**: `Chat with gemini 3 - MACS.md`

## What It Does
Claude Code Proxy sits between Claude Code CLI and your chosen API provider. Claude Code thinks it's talking to Anthropic, but you're actually using whatever provider you want—OpenRouter, Gemini, OpenAI, local models, etc.

## Features
- 💰 Save money (Gemini/OpenRouter vs Anthropic)
- 🏠 Run locally (Ollama/LM Studio)
- 🌐 Multi-provider Hybrid Mode
- 🧠 Extended Reasoning (O1/R1)

## Configuration
### Model Mapping
| Claude Requests | Routes To | Env Var |
|-----------------|-----------|---------|
| claude-opus-4 | BIG | `BIG_MODEL` |
| claude-sonnet-4 | MIDDLE | `MIDDLE_MODEL` |
| claude-haiku-4 | SMALL | `SMALL_MODEL` |

### Hybrid Mode Example
```bash
ENABLE_BIG_ENDPOINT="true"
BIG_ENDPOINT="http://localhost:11434/v1" # Local Ollama
BIG_MODEL="qwen2.5:72b"

MIDDLE_MODEL="anthropic/claude-sonnet-4" # OpenRouter

SMALL_MODEL="google/gemini-flash-1.5:free" # Free Tier
```

[See full file content in original source lines 3013-3826]
