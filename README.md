# Rails Tidy
This script runs multiple code quality tools:
- JavaScript & CSS ([Prettier](https://prettier.io) + [Import Sorting](https://github.com/trivago/prettier-plugin-sort-imports)) - Formats JS and CSS files
- HTML+ERB ([Herb Formatter](https://github.com/marcoroth/herb)) - Formats HTML+ERB templates
- HTML+ERB ([Herb Linter](https://github.com/marcoroth/herb)) - Lints HTML+ERB templates

Useful for [importmaps](https://github.com/rails/importmap-rails) projects that skip Node/npm — all tools run as standalone binaries with no build step required.


Usage:
1. Add to your `bin/` folder in your Rails app
2. Run the script 
- `bin/tidy` Check mode (no changes)
- `bin/tidy --fix` Fix mode (format and auto-fix)

All tools run in parallel. Output is displayed sequentially in headers.

---

For VScode users:

You could have this run automatically on save by adding it to your commands when using [vscode-runonsave](https://github.com/emeraldwalk/vscode-runonsave). Not the fastest but good enough if you want it to run automatically.

```json
 "emeraldwalk.runonsave": {
    "commands": [
      {
        "match": "\\.(js|css|html|erb)$",
        "cmd": "bin/tidy --fix",
      },
    ]
  },
```