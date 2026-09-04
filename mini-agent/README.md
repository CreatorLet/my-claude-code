# Mini Coding Agent

A small, independent coding-agent prototype built around a provider interface rather than the large Claude Code source snapshot.

## What it does

1. Starts in your terminal.
2. Lets you choose **Gemini** or **Anthropic**.
3. Prompts for the API key if it is not already in the environment.
4. Accepts a natural-language coding request.
5. Creates/reads/edits files inside `mini-agent/workspace/`.
6. Runs commands for dependency installation, builds, tests, and debugging.
7. Loops through tool calls until the model decides the work is complete.
8. Instructs the model to audit the project and fix verification failures before claiming completion.

## Requirements

- Node.js 20+
- A Gemini API key or Anthropic API key

## Install

From this directory:

```bash
npm install
npm run build
npm start
```

For development without a build:

```bash
npm run dev
```

The agent creates a `workspace` directory automatically. Your generated project stays there and is ignored by Git.

## Optional environment variables

Copy `.env.example` to `.env` and export the variables using your shell, or set them directly in the terminal. The program also accepts an API key interactively, so no `.env` file is required.

```text
GEMINI_API_KEY=...
ANTHROPIC_API_KEY=...
GEMINI_MODEL=gemini-2.5-flash
ANTHROPIC_MODEL=claude-sonnet-4-20250514
```

Do **not** commit real API keys.

## Important limitation

This is the local Section-1 prototype. Commands execute on the machine where the agent is running, so only run it in a workspace you trust. The hosted version must add isolated containers/sandboxes before allowing arbitrary generated code from multiple users.

## Next stages

- browser chat UI and live preview
- hosted agent workers
- isolated per-project sandboxes
- GitHub project sync
- deployment/runtime management
- accounts, usage limits, billing and moderation
