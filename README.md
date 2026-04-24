# claude-open-source

Thin local harness wrapper for launching the Claude-compatible open-source CLI
path against the approved OpenAI-compatible harness target.

## Local Environment

This repo must use its own ignored `.env`. Do not rely on `C:\Users\keith\dev\.env`
for harness routing because that shared file can contain real OpenAI credentials.

Expected local keys:

```dotenv
OPENAI_API_KEY=
OPENAI_BASE_URL=https://openrouter.ai/api/v1
OPENAI_MODEL=openai/gpt-oss-120b:free

OPENROUTER_API_KEY=
OPENROUTER_BASE_URL=https://openrouter.ai/api/v1
OPENROUTER_MODEL=openai/gpt-oss-120b:free

HARNESS_OPENROUTER_API_KEY=
HARNESS_OPENROUTER_BASE_URL=https://openrouter.ai/api/v1
HARNESS_OPENROUTER_MODEL=openai/gpt-oss-120b:free
```

For now, OpenRouter is the only callable harness LLM engine. The `OPENAI_*`
keys are local OpenAI-compatible harness target keys, not permission to call
the real OpenAI account from the shared dev environment.

## Wrapper

Use `claudeopen.py` or `claudeopen.cmd` to launch the Claude-compatible CLI
with the local OpenRouter target. The wrapper reads this repo's local `.env`,
locks the configured model, and isolates Claude config from any normal Claude
login state.
