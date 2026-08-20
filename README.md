# JC-kk/homebrew-tap

Homebrew casks for my own tools.

## Ambit

A menu bar control panel for what Claude Code and Codex can each load: skills, MCP servers and
subagents, with an independent switch per agent. Source and issues:
[JC-kk/ambit](https://github.com/JC-kk/ambit).

```bash
brew install --cask --no-quarantine JC-kk/tap/ambit
```

`--no-quarantine` is needed because Ambit is ad-hoc signed rather than notarised — notarisation
requires a paid Apple Developer Program membership. Without the flag, macOS quarantines the app and
refuses the first launch; you would then have to clear it yourself:

```bash
xattr -dr com.apple.quarantine /Applications/Ambit.app
```

Uninstalling never removes `~/.agent-capabilities`. That directory holds the only copy of every skill
and subagent Ambit manages, so it is left alone on purpose.
