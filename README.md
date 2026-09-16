# Software Inventory (Windows)

English | [简体中文](README.zh-CN.md)

A categorized inventory of the software installed on my Windows machine, with a short introduction and official links.

## Windows Installation Guides

Official Microsoft pages for downloading and installing Windows:

| Guide | Introduction | Link |
|---|---|---|
| Download Windows 11 | Official page with the Windows 11 Installation Assistant, the media creation tool and ISO downloads. | [microsoft.com](https://www.microsoft.com/software-download/windows11) |
| Ways to install Windows 11 | Microsoft Support article covering upgrade, clean install and installation media options. | [support.microsoft.com](https://support.microsoft.com/en-us/windows/deployment/install-upgrade/ways-to-install-windows-11) |
| Create installation media for Windows | Microsoft Support guide for a bootable USB drive or ISO file. | [support.microsoft.com](https://support.microsoft.com/en-us/windows/deployment/install-upgrade/create-installation-media-for-windows) |

## Table of Contents

- [Windows Installation Guides](#windows-installation-guides)
- [Managed with Scoop](#managed-with-scoop)
- [Installed Manually](#installed-manually)
- [AI Tools](#ai-tools)
- [LLM Clients and Front-ends](#llm-clients-and-front-ends)
- [Scope and Method](#scope-and-method)
- [License](#license)

## Managed with Scoop

**Scoop** is a command-line installer for Windows. It installs programs from community-maintained buckets into `~\scoop` without administrator rights and exposes their executables through shims, so upgrades and removals stay in one place.

- Official site: [scoop.sh](https://scoop.sh/)
- Install Scoop in PowerShell:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

The install command column uses the manifest name of the bucket each program lives in. Add the other buckets once before installing from them: `scoop bucket add extras` and `scoop bucket add java`.

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| 7-Zip | File archiver with a high compression ratio and a simple GUI. | [7-zip.org](https://www.7-zip.org/) | `scoop install 7zip` |
| Android Studio | Official IDE for Android app development, built on IntelliJ IDEA. | [developer.android.com](https://developer.android.com/studio) | `scoop install android-studio` |
| AutoHotkey | Scripting language for Windows automation and custom hotkeys. | [autohotkey.com](https://www.autohotkey.com/) | `scoop install autohotkey` |
| Bandizip | Fast archiver supporting ZIP, 7Z, RAR and more. | [bandisoft.com](https://www.bandisoft.com/bandizip/) | `scoop install bandizip` |
| bat | cat clone with syntax highlighting and Git integration. | [github.com/sharkdp](https://github.com/sharkdp/bat) | `scoop install bat` |
| BleachBit | Cross-platform disk cleaner and privacy tool for caches, logs and history. | [bleachbit.org](https://www.bleachbit.org/) | `scoop install bleachbit` |
| cmder | Portable console emulator bundling ConEmu and Clink. | [cmder.net](https://cmder.net/) | `scoop install cmder` |
| Dark (WiX) | Decompiler from the WiX toolset for Windows installer packages. | [wixtoolset.org](https://wixtoolset.org/) | `scoop install dark` |
| Dism++ | Portable Windows servicing and cleanup utility built on DISM. | [github.com/Chuyu-Team](https://github.com/Chuyu-Team/Dism-Multi-language) | `scoop install dismplusplus` |
| Ditto | Open-source clipboard manager that keeps a searchable history. | [github.com/sabrogden](https://github.com/sabrogden/Ditto) | `scoop install ditto` |
| Eclipse Temurin JDK 21 | Free OpenJDK build of Java 21 (LTS) from the Adoptium project. | [adoptium.net](https://adoptium.net/) | `scoop install temurin21-jdk` |
| fd | Fast, user-friendly alternative to find. | [github.com/sharkdp](https://github.com/sharkdp/fd) | `scoop install fd` |
| Geek Uninstaller | Portable uninstaller that also removes leftover files and registry keys. | [geekuninstaller.com](https://geekuninstaller.com/) | `scoop install geekuninstaller` |
| Git | Distributed version control system. | [git-scm.com](https://git-scm.com/) | `scoop install git` |
| GitHub CLI | Official command-line client for GitHub. | [cli.github.com](https://cli.github.com/) | `scoop install gh` |
| Helix | Modal text editor with built-in language server support. | [helix-editor.com](https://helix-editor.com/) | `scoop install helix` |
| IntelliJ IDEA | JetBrains IDE for JVM languages; the manifest installs the free Community edition. | [jetbrains.com/idea](https://www.jetbrains.com/idea/) | `scoop install idea` |
| jq | Command-line JSON processor. | [jqlang.github.io](https://jqlang.github.io/jq/) | `scoop install jq` |
| Make | GNU build automation tool. | [gnu.org/software/make](https://www.gnu.org/software/make/) | `scoop install make` |
| Microsoft Visual C++ Redistributable | Runtime libraries required by programs built with MSVC. | [learn.microsoft.com](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | `scoop install vcredist2022` |
| Microsoft VS Code | Extensible code editor with built-in Git, debugger and extensions. | [code.visualstudio.com](https://code.visualstudio.com/) | `scoop install vscode` |
| NekoBox (NekoRay) | Qt frontend for sing-box proxy cores; the upstream repository is archived. | [github.com/MatsuriDayo](https://github.com/MatsuriDayo/nekoray) | `scoop install nekobox` |
| Node.js | JavaScript runtime used for tooling and server-side code. | [nodejs.org](https://nodejs.org/) | `scoop install nodejs` |
| OBS Studio | Open-source live streaming and screen recording application. | [obsproject.com](https://obsproject.com/) | `scoop install obs-studio` |
| Oracle JDK 26 | Oracle OpenJDK distribution of Java 26. | [oracle.com/java](https://www.oracle.com/java/technologies/downloads/) | `scoop install oraclejdk` |
| pnpm | Fast, disk-efficient package manager for Node.js projects. | [pnpm.io](https://pnpm.io/) | `scoop install pnpm` |
| PotPlayer | Feature-rich multimedia player from Daum. | [potplayer.daum.net](https://potplayer.daum.net/) | `scoop install potplayer` |
| Python | General-purpose programming language and interpreter. | [python.org](https://www.python.org/) | `scoop install python` |
| Q-Dir | Quad-pane file manager with tabs and quick filter views. | [q-dir.com](https://www.q-dir.com/) | `scoop install q-dir` |
| QQ | Tencent instant messenger with file transfer and group chat. | [im.qq.com](https://im.qq.com/) | `scoop install qq` |
| ripgrep | Recursive search tool that respects gitignore rules. | [github.com/BurntSushi](https://github.com/BurntSushi/ripgrep) | `scoop install ripgrep` |
| Rust (rustup) | Toolchain installer and version manager for the Rust language. | [rust-lang.org](https://www.rust-lang.org/) | `scoop install rustup` |
| SpaceSniffer | Treemap view of disk space usage. | [uderzo.it](http://www.uderzo.it/main_products/space_sniffer/) | `scoop install spacesniffer` |
| Typora | Minimal Markdown editor with live preview and export. | [typora.io](https://typora.io/) | `scoop install typora` |
| WeChat | Tencent messaging, payment and mini-program client. | [weixin.qq.com](https://weixin.qq.com/) | `scoop install wechat` |
| WebStorm | JetBrains IDE for JavaScript and TypeScript development. | [jetbrains.com/webstorm](https://www.jetbrains.com/webstorm/) | `scoop install webstorm` |
| wget | Command-line downloader for HTTP, HTTPS and FTP. | [gnu.org/software/wget](https://www.gnu.org/software/wget/) | `scoop install wget` |
| WPS Office | Office suite with Writer, Spreadsheets, Presentation and PDF tools. | [wps.com](https://www.wps.com/) | `scoop install wpsoffice` |
| Zed | High-performance code editor written in Rust. | [zed.dev](https://zed.dev/) | `scoop install zed` |

## Installed Manually

These programs have no Scoop manifest, so they are installed from their official pages:

| Software | Introduction | Official site |
|---|---|---|
| AnyTXT Searcher | Desktop full-text search engine for local documents. | [anytxt.net](https://anytxt.net/) |
| Autovisor | Playwright-based unattended course player for online learning platforms. | [github.com/CXRunfree](https://github.com/CXRunfree/Autovisor) |
| Baidu Netdisk | Cloud storage client from Baidu. | [pan.baidu.com](https://pan.baidu.com/) |
| ContextMenuManager | Portable manager for Windows right-click context menu entries. | [github.com/BluePointLilac](https://github.com/BluePointLilac/ContextMenuManager) |
| DaVinci Resolve | Video editing, colour grading, visual effects and audio post-production suite. | [blackmagicdesign.com](https://www.blackmagicdesign.com/products/davinciresolve) |
| Docker Desktop | Container platform for building and running Linux containers on Windows. | [docker.com](https://www.docker.com/) |
| LifeLog | Local-first personal life log with tags, full-text search and Markdown or Excel export. | [github.com/Zzz210s](https://github.com/Zzz210s/LifeLog) |
| Microsoft Rewards Script | TypeScript and Playwright bot that automates daily Microsoft Rewards tasks. | [github.com/TheNetsky](https://github.com/TheNetsky/Microsoft-Rewards-Script) |
| Microsoft Visual Studio Build Tools 2026 | MSVC compiler, linker and Windows SDK toolchain for building C++ projects. | [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/) |
| MinGW-Builds (GCC) | GCC C and C++ toolchain for Windows, built from the MinGW-w64 sources. | [github.com/niXman](https://github.com/niXman/mingw-builds-binaries) |
| NetEase Cloud Music | Music streaming client with personalised recommendations and social features. | [music.163.com](https://music.163.com/) |
| PDF24 Creator | Free offline toolkit to create, merge, compress and edit PDF files. | [pdf24.org](https://www.pdf24.org/en/) |
| pineapple-pictures | Lightweight Qt image viewer with basic editing. | [github.com/BLumia](https://github.com/BLumia/pineapple-pictures) |
| PixPin | Screenshot, pin-to-screen, long-capture, OCR and screen-recording tool. | [pixpin.com](https://pixpin.com/) |
| QGIS | Open-source geographic information system for viewing and analysing spatial data. | [qgis.org](https://qgis.org/) |
| Quark Cloud Drive | Cloud storage desktop client from Quark. | [pan.quark.cn](https://pan.quark.cn/) |
| Watt Toolkit (Steam++) | Network accelerator and script toolkit for Steam, GitHub and other services. | [steampp.net](https://steampp.net/) |
| WeChat DevTools | Official IDE for developing WeChat Mini Programs and Official Accounts. | [developers.weixin.qq.com](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) |
| WeLink | Huawei Cloud enterprise collaboration and video conferencing client. | [huaweicloud.com](https://www.huaweicloud.com/product/welink.html) |
| Xshell | SSH and Telnet terminal client for Windows; the home edition is free. | [xshell.com](https://www.xshell.com/) |

## AI Tools

Tools that support AI coding workflows on this machine:

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| CC Switch | Cross-platform manager that switches provider configs for Claude Code, Codex and other AI CLI agents. | [github.com/farion1231](https://github.com/farion1231/cc-switch) | `scoop install cc-switch` |
| CCTO | Claude Code Token Optimizer: cuts token usage with local semantic indexing and MCP tools. | [github.com/alidhibi](https://github.com/alidhibi/ccto) | `npm install -g @alidhibi/ccto` |
| Chrome DevTools MCP | MCP server that lets AI agents inspect and drive Chrome DevTools. | [github.com/ChromeDevTools](https://github.com/ChromeDevTools/chrome-devtools-mcp) | `npm install -g chrome-devtools-mcp` |
| OpenCommit | Generates git commit messages with an LLM from the staged diff. | [github.com/di-sukharev](https://github.com/di-sukharev/opencommit) | `npm install -g opencommit` |

## LLM Clients and Front-ends

Clients and command-line front-ends for large language models:

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Claude Code | Anthropic's terminal coding agent for Claude models. | [github.com/anthropics](https://github.com/anthropics/claude-code) | `scoop install claude-code` |
| OpenCode Desktop | Desktop client for the OpenCode AI coding agent. | [opencode.ai](https://opencode.ai/) | `scoop install opencode-desktop` |
| pi | Coding agent CLI with read, bash, edit and write tools plus session management. | [github.com/earendil-works](https://github.com/earendil-works/pi) | `npm install -g @earendil-works/pi-coding-agent` |

## Scope and Method

Compiled on 2026-09-15 from three sources on my Windows machine:

- the top level of the `E:\` software drive;
- packages installed with Scoop (`scoop list`);
- system-wide and user-local development tools under `C:\Program Files`, `C:\Program Files (x86)` and `%LOCALAPPDATA%\Programs`.

Programs are grouped by how they are best installed: the Scoop section lists the exact manifest name for the install command, everything else is installed from its official page, and AI-related programs have their own sections. Scoop manifest names were matched against the `main`, `extras` and `java` buckets.

Windows system folders, build output directories and dependency-only packages are left out: `$RECYCLE.BIN`, `Config.Msi`, `System Volume Information`, `0-cargo-target` and the `cacert` certificate bundle.

Every link was opened and checked for reachability while writing this list. Entries without a public homepage are linked to their official repository instead.

## License

[MIT](LICENSE)
