# pi-zed-terminal-title

Pi extension for Zed Terminal Threads.

Features:

- Sets Zed terminal title while Pi works/idles
- `⏳️ <title>` while working, plain `<title>` when idle
- Generates a short AI title from the first user prompt
- Persists/restores the title across `/resume`
- Emits terminal bell on agent completion for Zed notifications
- Supports configurable cheap/fast title model

## Install

Install from GitHub:

```bash
pi install git:git@github.com:chiroro-jr/pi-zed-terminal-title.git
```

Or with HTTPS:

```bash
pi install https://github.com/chiroro-jr/pi-zed-terminal-title
```

Try for one run without installing:

```bash
pi -e git:git@github.com:chiroro-jr/pi-zed-terminal-title.git
```

For local development:

```bash
pi install /home/dennis/Documents/codespaces/personal/pi-zed-terminal-title
```

## Configure title model

In `~/.pi/agent/settings.json` or project `.pi/settings.json`:

```json
{
  "terminalThreadTitleModel": "openai-codex/gpt-5.4-mini"
}
```

If unset, invalid, or unavailable, the extension falls back to the active Pi model, then a local title derived from the prompt.

## Zed sound settings

For sound notifications, enable Zed agent sound settings, for example:

```json
{
  "agent": {
    "notify_when_agent_waiting": "primary_screen",
    "play_sound_when_agent_done": "always"
  }
}
```

Use `"always"` while testing if the terminal remains visible.
