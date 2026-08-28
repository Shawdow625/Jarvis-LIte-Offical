# jarvis-lite

A stripped-down, public starter kit for running your own "Jarvis" — a
personal AI assistant with a persistent identity and a growing memory
vault. Two ways to run it, pick whichever fits:

- **`jarvis.py`** — plain Python, talks to the Anthropic API directly. Only
  needs an API key (pay-as-you-go, no Claude Pro/Max subscription required).
  This is the one to use if you don't have Claude Code or a paid Claude plan.
- **Claude Code** — the full agent experience (file access, tools, richer
  memory handling). Needs [Claude Code](https://claude.com/product/claude-code)
  installed, and either a Claude Pro/Max login or an API key.

This is the *lite* version: no personal content, no hidden features, no
machine-specific setup baked in — just the scaffolding. Make it yours.

## What's in here

| Path | What it is |
|---|---|
| `jarvis.py` | Standalone chat client using just the Anthropic API — no Claude Code needed. Reads `CLAUDE.md` and the vault for context, logs each session to today's daily note. |
| `CLAUDE.md` | Identity and boot rules. Read automatically by Claude Code sessions in this folder; also fed to `jarvis.py` as its system prompt. Edit this to change the name, tone, and standing rules. |
| `memory-vault/` | An empty [Obsidian](https://obsidian.md/) vault — daily notes, an overview folder, a projects folder, and an index (`VAULT-INDEX.md`) tying it together. This is where persistent memory actually lives. |
| `voice-line/` | Instructions for wiring up [backtalk](https://github.com/jaredrhod/backtalk) (external, open-source) as a push-to-talk voice line for the same identity/vault (Claude Code path only). |

## Option A: no Claude Code, just an API key (recommended if you don't have Pro/Max)

1. Install [Python](https://www.python.org/) 3.11+ and [Git](https://git-scm.com/).
2. `git clone <this repo's URL>` and open the folder.
3. Get an API key at [console.anthropic.com](https://console.anthropic.com/)
   — pay-as-you-go, works with no Claude.ai subscription at all.
4. Double-click **`setup-api.bat`** once — creates a virtual environment,
   installs dependencies, and opens `.env` for you to paste the key into.
5. Double-click **`start-chat-api.bat`** to talk to Jarvis.

Usage is billed per token to whoever's API key is in `.env` — cheap for
casual chatting, but it's real money, not free like a subscription's
included usage. Each friend running this should use their own key.

## Option B: Claude Code (full agent, needs Pro/Max or an API key)

1. Install [Git](https://git-scm.com/) and [Claude Code](https://claude.com/product/claude-code) —
   `npm install -g @anthropic-ai/claude-code`, then sign in (Claude.ai
   account with a Pro/Max plan, or an `ANTHROPIC_API_KEY`).
2. `git clone <this repo's URL>` and open the folder.
3. Double-click **`start-chat.bat`** — picks up `CLAUDE.md` and the vault
   automatically, and gets real file/tool access on top of plain chat.
4. For a voice line, follow `voice-line/README.md`.

Either option runs on **your own** Claude access — nothing here is tied to
whoever wrote it, and there's no shared or bundled credential anywhere in
this repo.

## Making it yours

- Edit `CLAUDE.md` — change the name, the tone, add your own standing
  rules as you find you want them repeated across sessions. Both `jarvis.py`
  and Claude Code read this same file.
- The vault starts empty on purpose. It fills in the same way any real
  setup does: use it, and checkpoint discipline (see `CLAUDE.md`) keeps it
  from turning into a junk drawer.
- Nothing here is wired to auto-approve destructive actions by default —
  loosen permissions deliberately, once you understand what you're
  loosening, not by default.

## License

MIT — see `LICENSE`.
