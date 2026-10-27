# Code Explainer

A CUGA-powered demo app that explains code snippets to beginners. Paste any snippet — in any language — and the agent identifies the language, explains what it does in plain English, walks through it line by line, and (for Python) checks whether it is syntactically valid.

## Port

**28838**

## Quick start

```bash
# Install dependencies
pip install -r requirements.txt

# Set required env vars (example: OpenAI)
export LLM_PROVIDER=openai
export LLM_MODEL=gpt-4o
export OPENAI_API_KEY=<your-key>
export AGENT_SETTING_CONFIG=/path/to/settings.toml

# Run
python main.py --port 28838

# Open in browser
open http://127.0.0.1:28838
```

## Example prompts

1. `Explain: for i in range(3): print(i * i)`
2. `What does this do? const add = (a, b) => a + b;`
3. `Explain this SQL: SELECT name FROM users WHERE age > 30`
4. `Is this valid Python? def f(x) return x`
5. `Walk me through a list comprehension: [x for x in range(10) if x % 2 == 0]`

## Tools

All tools come from the `code` MCP server — no API key needed to load them.

| Tool | Description |
|---|---|
| `detect_language` | Identifies the programming language of a code snippet |
| `check_python_syntax` | Validates Python syntax and reports errors with line numbers |
| `extract_code_metrics` | Returns basic metrics (line count, complexity) for a snippet |
