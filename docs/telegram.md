# Telegram Deploy Notification

A Rake task (`telegram:deploy_notify`) that sends a Telegram message after each deploy with the branch name, short commit SHA, and commit message. It fetches the latest push activity from the GitHub API and posts a formatted notification via the Telegram Bot API.

## Environment Variables

| Variable | Description |
|---|---|
| `TELEGRAM_BOT_TOKEN` | Telegram bot API token |
| `TELEGRAM_CHAT_ID` | Target chat/channel ID |
| `GITHUB_TOKEN` | GitHub personal access token |
| `GITHUB_REPO` | Repository in `owner/repo` format |

## Usage

- `bin/rails telegram:deploy_notify`
