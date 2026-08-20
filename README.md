# JC-kk/homebrew-tap

Homebrew casks for my own tools.

## Ambit

A menu bar control panel for what Claude Code and Codex can each load: skills, MCP servers and
subagents, with an independent switch per agent. Source and issues:
[JC-kk/ambit](https://github.com/JC-kk/ambit).

```bash
brew install --cask JC-kk/tap/ambit
xattr -dr com.apple.quarantine /Applications/Ambit.app
```

The second line is needed because Ambit is ad-hoc signed rather than notarised — notarisation
requires a paid Apple Developer Program membership. The quarantine flag comes from downloading the
disk image rather than from Homebrew, and brew copies the app out of the mounted volume without
stripping it, so a `brew install` needs it just like a manual download would.

(`--no-quarantine` no longer exists: Homebrew 6 removed the flag because its own quarantine support
is compiled out. It would not have helped here anyway.)

Uninstalling never removes `~/.agent-capabilities`. That directory holds the only copy of every skill
and subagent Ambit manages, so it is left alone on purpose.
