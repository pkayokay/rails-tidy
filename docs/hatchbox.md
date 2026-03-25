# Hatchbox

## Option 1: Zsh Function
A shell function you source in your `~/.zshrc`. App configs (name and SSH target) are defined directly in the script, so you can manage multiple apps from anywhere without a `.env` file.

We recommend placing the file in `~/.config/hatchbox/hatchbox.zsh` and sourcing it from your `~/.zshrc`:

```zsh
source ~/.config/hatchbox/hatchbox.zsh
```

Usage:
- `hatchbox myapp` — Open a plain SSH session
- `hatchbox myapp console` — Start a Rails console
- `hatchbox myapp current` — Open a shell in the current release directory
- `hatchbox myapp logs server` — Tail server logs

## Option 2: Bin Script
A convenience wrapper for SSH-ing into [Hatchbox](https://www.hatchbox.io)-deployed Rails apps. Supports opening a plain SSH session, launching a Rails console, opening a shell in the current release directory, and tailing systemd journal logs.

Configuration is via a `.env` file in your project root:

| Variable | Description |
|---|---|
| `SSH_APP_NAME` | **(required)** App path on the server |

Connection is resolved using **one** of the following (first takes precedence):

| Option | Variables needed |
|---|---|
| SSH config alias | `SSH_HOST_ALIAS` (matches a host in `~/.ssh/config`) |
| Direct host | `SSH_HOST` (connects as `deploy@SSH_HOST`) |

Usage:
- `bin/hatchbox` — Open a plain SSH session
- `bin/hatchbox console` — Start a Rails console
- `bin/hatchbox current` — Open a shell in the current release directory
- `bin/hatchbox logs server` — Tail server logs
- `bin/hatchbox logs solid_queue` — Tail queue worker logs
