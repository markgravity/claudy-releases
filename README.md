<div align="center">
  <img src="https://raw.githubusercontent.com/markgravity/Claudy/main/assets/banner.png" width="200" height="200" alt="Claudy banner" />

  <h1>Claudy</h1>
  <p><strong>A native macOS app that gives Claude Code a proper home — multi-session, multi-account, all in one window.</strong></p>

  <p>
    Built with <a href="https://developer.apple.com/xcode/swiftui/">SwiftUI</a>,
    <a href="https://developer.apple.com/documentation/appkit">AppKit</a>,
    <a href="https://developer.apple.com/documentation/swiftdata">SwiftData</a>, and
    <a href="https://github.com/migueldeicaza/SwiftTerm">SwiftTerm</a>.
  </p>

  <p>
    <a href="#features">Features</a> •
    <a href="#install">Install</a> •
    <a href="#build-from-source">Build from source</a> •
    <a href="#contributing">Contributing</a> •
    <a href="#license">License</a>
  </p>

  <p>
    <a href="https://github.com/markgravity/claudy-releases/releases"><img src="https://img.shields.io/github/v/release/markgravity/claudy-releases" alt="Latest Release" /></a>
    <a href="https://github.com/markgravity/Claudy/actions/workflows/ci.yml"><img src="https://github.com/markgravity/Claudy/actions/workflows/ci.yml/badge.svg" alt="CI" /></a>
    <a href="https://www.gnu.org/licenses/gpl-3.0"><img src="https://img.shields.io/badge/License-GPLv3-blue.svg" alt="License: GPL v3" /></a>
  </p>
</div>

## Features

- **Multi-project sessions** — open and switch between projects in the sidebar; each project gets its own Claude Code instance
- **Multi-account switching** — configure multiple Claude accounts per project; Claudy automatically switches when one account approaches its usage limit
- **Usage tracking** — live usage bars for each account pulled directly from the Claude API
- **Native macOS terminal** — full-featured terminal powered by SwiftTerm
- **Draft commits** — save and restore git-based draft commits to preserve work-in-progress across sessions
- **Session resume** — sessions persist across app restarts via Claude Code's `--resume` flag
- **Idle detection** — Dock badge bounces when Claude is waiting for input
- **Plugin marketplace** — extend Claudy with community plugins
- **Auto-update** — in-app update checks with one-click install

## Requirements

- macOS 15.0+ (Sequoia or later)
- [Claude Code CLI](https://github.com/anthropics/claude-code) installed (default path: `/usr/local/bin/claude`)
- Xcode 26.3+ for local builds

## Install

### Download a release

1. Go to [Releases](https://github.com/markgravity/claudy-releases/releases)
2. Download the latest `Claudy.zip`
3. Extract and move `Claudy.app` to `/Applications`
4. Launch Claudy
5. Go to **Settings → General** and confirm the path to your `claude` binary

### Build from source

1. Clone the repository:

```bash
git clone https://github.com/markgravity/Claudy.git
cd Claudy
```

2. Open the project:

```bash
open Claudy.xcodeproj
```

3. Build and run with `Cmd+R`

You can also build from the terminal:

```bash
xcodebuild -project Claudy.xcodeproj -scheme Claudy -configuration Debug build
```

> **Note:** App Sandbox is disabled — this is required so Claudy can spawn the `claude` CLI subprocess.

## Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Swift 6.2 |
| UI Framework | SwiftUI |
| Persistence | SwiftData |
| Terminal | SwiftTerm (`LocalProcessTerminalView`) |
| Concurrency | Swift Structured Concurrency (`@Observable`, `@MainActor`) |

## Contributing

Contributions are welcome! Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## Star History

<a href="https://www.star-history.com/?repos=markgravity%2FCludy&type=date&logscale=&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/image?repos=markgravity/Claudy&type=date&theme=dark&logscale&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/image?repos=markgravity/Claudy&type=date&logscale&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/image?repos=markgravity/Claudy&type=date&logscale&legend=top-left" />
 </picture>
</a>

## License

GNU General Public License v3.0. See [LICENSE](LICENSE).
