# opencode config

Personal configuration for [opencode](https://opencode.ai) — custom agents, commands, and plugins.

## Structure

```
├── agents/                 # Custom agent definitions
│   ├── code-reviewer-agent.md
│   └── security-agent.md
├── commands/               # Custom slash commands
│   └── commit-push-all.md
├── plugins/                # Runtime plugins
│   ├── env-protection.js
│   └── notification.js
├── opencode.json           # Main config
├── opencode.jsonc          # JSONC variant (comments supported)
└── package.json
```
