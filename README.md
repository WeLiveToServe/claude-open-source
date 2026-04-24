# claude-open-source

Thin local harness repo for the Claude-compatible open-source CLI path. Wrapper
implementation now lives in the canonical `C:\Users\keith\dev\cli-harness`
checkout; files in this repo are compatibility shims for older paths.

## Local Environment

This repo must use its own ignored `.env`. Do not rely on `C:\Users\keith\dev\.env`
for harness routing because that shared file can contain real OpenAI credentials.

Expected local keys:

```dotenv
OPENROUTER_API_KEY=
OPENROUTER_BASE_URL=https://openrouter.ai/api/v1
OPENROUTER_MODEL=openai/gpt-oss-120b:free

HARNESS_OPENROUTER_API_KEY=
HARNESS_OPENROUTER_BASE_URL=https://openrouter.ai/api/v1
HARNESS_OPENROUTER_MODEL=openai/gpt-oss-120b:free
```

For now, OpenRouter is the only callable harness LLM engine. Do not put
`OPENAI_MODEL` or `OPENAI_BASE_URL` in the shared `C:\Users\keith\dev\.env`;
use the local harness `.env` keys above or process-scoped overrides.

## Wrapper

Use `C:\Users\keith\dev\cli-harness\claude-os.cmd` for new launches. The legacy
`claudeopen.py` and `claudeopen.cmd` files in this repo forward to that canonical
wrapper and accept the same options, including `--psycho`.
