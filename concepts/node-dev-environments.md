---
type: Guide
title: Node.js dev environments
description: "Switching Node.js versions: fnm, mise, nvm and Volta compared, with a recommendation."
tags:
  - javascript
  - nodejs
  - version-manager
  - guide
sources:
  - id: node-vm
    resource: /sources/node-version-managers.md
    title: nvm, fnm, Volta and mise docs
  - id: homebrew
    resource: /sources/homebrew-api-dev-envs.md
    title: Homebrew API snapshot (dev environments)
---
# Node.js dev environments

## Recommendation: fnm, or mise for multiple languages

- **Node.js only: use fnm.** It runs on macOS, Windows and Linux, is a single fast binary, reads both `.nvmrc` and `.node-version`, and can switch versions automatically when you `cd` into a project (`--use-on-cd`). It installs with Homebrew, winget, Scoop or Chocolatey.[^node-vm]
- **Node.js plus other runtimes: use mise.** One tool manages Node.js and other languages. It installs official nodejs.org builds, pins versions per project in `mise.toml`, and can also read `.nvmrc`, `.node-version` and `package.json` once you enable that setting. Volta's maintainers recommend mise as Volta's replacement.[^node-vm]
- **Avoid starting new setups on Volta.** It's unmaintained, and its maintainers say future OS or ecosystem changes won't be fixed.[^node-vm]
- **nvm is fine if you already use it.** It only runs in POSIX shells (macOS, Linux, WSL, Git Bash or Cygwin), not natively on Windows, and its maintainers don't support installing it through Homebrew.[^node-vm] [^homebrew]

## Comparison

| | fnm | mise | nvm | Volta |
| --- | --- | --- | --- | --- |
| Scope | Node.js | Many runtimes, env vars, tasks | Node.js | JS toolchain |
| Native Windows | Yes | | No (WSL, Git Bash, Cygwin; or nvm-windows, a separate project) | |
| Version files | `.nvmrc`, `.node-version` | `mise.toml`; `.nvmrc`, `.node-version`, `package.json` once enabled | `.nvmrc` | |
| Auto-switch on `cd` | `fnm env --use-on-cd` | Per-project config | Needs a shell hook or zsh plugin | |
| Homebrew | `brew install fnm` (recommended on macOS) | `brew install mise` | Formula exists but upstream doesn't support it | `brew install volta` |
| Licence | GPL-3.0 | MIT | MIT | |
| Status | Maintained | Maintained | Maintained | **Unmaintained** |

Sources: version manager docs[^node-vm], Homebrew[^homebrew].

## Package managers

npm comes with Node.js. mise can also install and pin npm, pnpm and Yarn as separate tools, without needing Corepack.[^node-vm]

## Setup with fnm

```sh
brew install fnm
# add to ~/.zshrc
eval "$(fnm env --use-on-cd --shell zsh)"
fnm install --lts
echo "<version>" > .node-version   # pin the project; fnm switches on cd
```

On Windows, run `winget install Schniz.fnm` or `choco install fnm`, then add `fnm env --use-on-cd --shell powershell | Out-String | Invoke-Expression` to your PowerShell profile.[^node-vm]

## Setup with mise

```sh
brew install mise
mise use node@lts         # writes mise.toml in this project
mise use -g node@lts      # personal default
mise settings add idiomatic_version_file_enable_tools node   # also read .nvmrc / .node-version
```

These commands are from the mise docs.[^node-vm] The Homebrew formula is `mise`.[^homebrew]

## See also

- [Python dev environments](./python-dev-environments.md)
- [WSL](../tools/wsl.md)
- [Local machine setup](./local-machine-setup.md)

[^node-vm]: [nvm, fnm, Volta and mise docs](../sources/node-version-managers.md)
[^homebrew]: [Homebrew API snapshot (dev environments)](../sources/homebrew-api-dev-envs.md)
