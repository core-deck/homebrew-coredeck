# homebrew-coredeck

Homebrew tap for [Core Deck](https://github.com/core-deck/core-deck) — a hardware control surface for Claude Code.

## Install

```bash
brew install --cask core-deck/coredeck/coredeck
coredeck setup
```

`brew install` drops `Core Deck.app` into `/Applications` and exposes
both `coredeck` and `coredeck-claude` on your `PATH`. `coredeck setup`
installs the Claude Code hooks (`~/.claude/settings.json`) and registers
the launchd auto-start agent. To run Claude under CoreDeck, alias
`claude` to the wrapper in your shell rc:

```bash
echo 'alias claude="coredeck-claude"' >> ~/.zshrc
```

## Uninstall

```bash
brew uninstall --cask coredeck
```

The cask's `uninstall` stanza unloads the launchd agent before
removing the app. To clean up Claude Code hook config, daemon logs,
and the launchd plist as well:

```bash
brew uninstall --cask --zap coredeck
```

## Releases

The cask is bumped manually for each [release](https://github.com/core-deck/core-deck/releases) of the main repo. The canonical source lives at [`macos/Casks/coredeck.rb`](https://github.com/core-deck/core-deck/blob/main/macos/Casks/coredeck.rb) in the main repo and is copied here on each release with the published DMG digest.

## License

The cask file itself is BSD-2-Clause, matching Homebrew's tap convention. The CoreDeck app it points at is GPL-3.0-or-later.
