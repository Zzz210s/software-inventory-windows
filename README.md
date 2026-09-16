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
- [Development Tools](#development-tools)
  - [IDE and Editors](#ide-and-editors)
  - [Runtimes and Package Managers](#runtimes-and-package-managers)
  - [Terminal and Command-line Tools](#terminal-and-command-line-tools)
  - [Build and Container Toolchains](#build-and-container-toolchains)
- [System and Productivity](#system-and-productivity)
  - [System Maintenance and Cleanup](#system-maintenance-and-cleanup)
  - [Files and Compression](#files-and-compression)
  - [Clipboard and Screenshots](#clipboard-and-screenshots)
  - [Automation](#automation)
- [Documents and Office](#documents-and-office)
- [Networking and Cloud](#networking-and-cloud)
  - [Proxy and Acceleration](#proxy-and-acceleration)
  - [Cloud Storage and Sync](#cloud-storage-and-sync)
- [Media and Graphics](#media-and-graphics)
- [Communication and Meetings](#communication-and-meetings)
- [Science and Personal Data](#science-and-personal-data)
- [AI Tools](#ai-tools)
- [LLM Clients and Front-ends](#llm-clients-and-front-ends)
- [Scope and Method](#scope-and-method)
- [License](#license)

## Development Tools

### IDE and Editors

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Android Studio | Official IDE for Android app development, built on IntelliJ IDEA. | [developer.android.com](https://developer.android.com/studio) | `winget install Google.AndroidStudio` |
| IntelliJ IDEA | JetBrains IDE for JVM languages; the manifest installs the free Community edition. | [jetbrains.com/idea](https://www.jetbrains.com/idea/) | `winget install JetBrains.IntelliJIDEA.Ultimate` |
| Microsoft VS Code | Extensible code editor with built-in Git, debugger and extensions. | [code.visualstudio.com](https://code.visualstudio.com/) | `winget install Microsoft.VisualStudioCode` |
| WeChat DevTools | Official IDE for developing WeChat Mini Programs and Official Accounts. | [developers.weixin.qq.com](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) | `winget install Tencent.WeixinDevTools` |
| WebStorm | JetBrains IDE for JavaScript and TypeScript development. | [jetbrains.com/webstorm](https://www.jetbrains.com/webstorm/) | `winget install JetBrains.WebStorm` |
| Zed | High-performance code editor written in Rust. | [zed.dev](https://zed.dev/) | `winget install ZedIndustries.Zed` |

### Runtimes and Package Managers

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Eclipse Temurin JDK 21 | Free OpenJDK build of Java 21 (LTS) from the Adoptium project. | [adoptium.net](https://adoptium.net/) | `winget install EclipseAdoptium.Temurin.21.JDK` |
| Node.js | JavaScript runtime used for tooling and server-side code. | [nodejs.org](https://nodejs.org/) | `winget install OpenJS.NodeJS` |
| Oracle JDK 26 | Oracle OpenJDK distribution of Java 26. | [oracle.com/java](https://www.oracle.com/java/technologies/downloads/) | `winget install Oracle.JDK.26` |
| pnpm | Fast, disk-efficient package manager for Node.js projects. | [pnpm.io](https://pnpm.io/) | `winget install pnpm.pnpm` |
| Python | General-purpose programming language and interpreter. | [python.org](https://www.python.org/) | `winget install Python.Python.3.14` |
| Rust (rustup) | Toolchain installer and version manager for the Rust language. | [rust-lang.org](https://www.rust-lang.org/) | `winget install Rustlang.Rustup` |

### Terminal and Command-line Tools

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| bat | cat clone with syntax highlighting and Git integration. | [github.com/sharkdp](https://github.com/sharkdp/bat) | `winget install sharkdp.bat` |
| cmder | Portable console emulator bundling ConEmu and Clink. | [cmder.net](https://cmder.net/) | Manual install |
| Dark (WiX) | Decompiler from the WiX toolset for Windows installer packages. | [wixtoolset.org](https://wixtoolset.org/) | Manual install |
| fd | Fast, user-friendly alternative to find. | [github.com/sharkdp](https://github.com/sharkdp/fd) | `winget install sharkdp.fd` |
| Git | Distributed version control system. | [git-scm.com](https://git-scm.com/) | `winget install Git.Git` |
| GitHub CLI | Official command-line client for GitHub. | [cli.github.com](https://cli.github.com/) | `winget install GitHub.cli` |
| Helix | Modal text editor with built-in language server support. | [helix-editor.com](https://helix-editor.com/) | `winget install Helix.Helix` |
| jq | Command-line JSON processor. | [jqlang.github.io](https://jqlang.github.io/jq/) | `winget install jqlang.jq` |
| Make | GNU build automation tool. | [gnu.org/software/make](https://www.gnu.org/software/make/) | `winget install ezwinports.make` |
| ripgrep | Recursive search tool that respects gitignore rules. | [github.com/BurntSushi](https://github.com/BurntSushi/ripgrep) | `winget install BurntSushi.ripgrep.MSVC` |
| wget | Command-line downloader for HTTP, HTTPS and FTP. | [gnu.org/software/wget](https://www.gnu.org/software/wget/) | `winget install JernejSimoncic.Wget` |
| Xshell | SSH and Telnet terminal client for Windows; the home edition is free. | [xshell.com](https://www.xshell.com/) | Manual install |

### Build and Container Toolchains

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Docker Desktop | Container platform for building and running Linux containers on Windows. | [docker.com](https://www.docker.com/) | `winget install Docker.DockerDesktop` |
| Microsoft Visual C++ Redistributable | Runtime libraries required by programs built with MSVC. | [learn.microsoft.com](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | `winget install "Microsoft.VCRedist.2015+.x64"` |
| Microsoft Visual Studio Build Tools 2026 | MSVC compiler, linker and Windows SDK toolchain for building C++ projects. | [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/) | Manual install |
| MinGW-Builds (GCC) | GCC C and C++ toolchain for Windows, built from the MinGW-w64 sources. | [github.com/niXman](https://github.com/niXman/mingw-builds-binaries) | Manual install |

## System and Productivity

### System Maintenance and Cleanup

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| BleachBit | Cross-platform disk cleaner and privacy tool for caches, logs and history. | [bleachbit.org](https://www.bleachbit.org/) | `winget install BleachBit.BleachBit` |
| ContextMenuManager | Portable manager for Windows right-click context menu entries. | [github.com/BluePointLilac](https://github.com/BluePointLilac/ContextMenuManager) | `winget install BluePointLilac.ContextMenuManager` |
| Dism++ | Portable Windows servicing and cleanup utility built on DISM. | [github.com/Chuyu-Team](https://github.com/Chuyu-Team/Dism-Multi-language) | `winget install "ChuyuTeam.DISM++"` |
| Geek Uninstaller | Portable uninstaller that also removes leftover files and registry keys. | [geekuninstaller.com](https://geekuninstaller.com/) | `winget install GeekUninstaller.GeekUninstaller` |
| SpaceSniffer | Treemap view of disk space usage. | [uderzo.it](http://www.uderzo.it/main_products/space_sniffer/) | `winget install UderzoSoftware.SpaceSniffer` |

### Files and Compression

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| 7-Zip | File archiver with a high compression ratio and a simple GUI. | [7-zip.org](https://www.7-zip.org/) | `winget install 7zip.7zip` |
| Bandizip | Fast archiver supporting ZIP, 7Z, RAR and more. | [bandisoft.com](https://www.bandisoft.com/bandizip/) | `winget install Bandisoft.Bandizip` |
| Q-Dir | Quad-pane file manager with tabs and quick filter views. | [q-dir.com](https://www.q-dir.com/) | `winget install SoftwareOK.Q-Dir` |

### Clipboard and Screenshots

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Ditto | Open-source clipboard manager that keeps a searchable history. | [github.com/sabrogden](https://github.com/sabrogden/Ditto) | `winget install Ditto.Ditto` |
| PixPin | Screenshot, pin-to-screen, long-capture, OCR and screen-recording tool. | [pixpin.com](https://pixpin.com/) | `winget install PixPin.PixPin` |

### Automation

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| AutoHotkey | Scripting language for Windows automation and custom hotkeys. | [autohotkey.com](https://www.autohotkey.com/) | `winget install AutoHotkey.AutoHotkey` |
| Autovisor | Playwright-based unattended course player for online learning platforms. | [github.com/CXRunfree](https://github.com/CXRunfree/Autovisor) | Manual install |
| Microsoft Rewards Script | TypeScript and Playwright bot that automates daily Microsoft Rewards tasks. | [github.com/TheNetsky](https://github.com/TheNetsky/Microsoft-Rewards-Script) | Manual install |

## Documents and Office

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| AnyTXT Searcher | Desktop full-text search engine for local documents. | [anytxt.net](https://anytxt.net/) | `winget install AnyTXT.AnyTXTSearcher` |
| PDF24 Creator | Free offline toolkit to create, merge, compress and edit PDF files. | [pdf24.org](https://www.pdf24.org/en/) | `winget install geeksoftwareGmbH.PDF24Creator` |
| Typora | Minimal Markdown editor with live preview and export. | [typora.io](https://typora.io/) | `winget install appmakes.Typora` |
| WPS Office | Office suite with Writer, Spreadsheets, Presentation and PDF tools. | [wps.com](https://www.wps.com/) | `winget install Kingsoft.WPSOffice` |

## Networking and Cloud

### Proxy and Acceleration

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| NekoBox (NekoRay) | Qt frontend for sing-box proxy cores; the upstream repository is archived. | [github.com/MatsuriDayo](https://github.com/MatsuriDayo/nekoray) | Manual install |
| Watt Toolkit (Steam++) | Network accelerator and script toolkit for Steam, GitHub and other services. | [steampp.net](https://steampp.net/) | Manual install |

### Cloud Storage and Sync

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Baidu Netdisk | Cloud storage client from Baidu. | [pan.baidu.com](https://pan.baidu.com/) | `winget install Baidu.BaiduNetdisk` |
| Quark Cloud Drive | Cloud storage desktop client from Quark. | [pan.quark.cn](https://pan.quark.cn/) | `winget install Alibaba.QuarkCloudDrive` |

## Media and Graphics

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| DaVinci Resolve | Video editing, colour grading, visual effects and audio post-production suite. | [blackmagicdesign.com](https://www.blackmagicdesign.com/products/davinciresolve) | Manual install |
| NetEase Cloud Music | Music streaming client with personalised recommendations and social features. | [music.163.com](https://music.163.com/) | `winget install NetEase.CloudMusic` |
| OBS Studio | Open-source live streaming and screen recording application. | [obsproject.com](https://obsproject.com/) | `winget install OBSProject.OBSStudio` |
| pineapple-pictures | Lightweight Qt image viewer with basic editing. | [github.com/BLumia](https://github.com/BLumia/pineapple-pictures) | Manual install |
| PotPlayer | Feature-rich multimedia player from Daum. | [potplayer.daum.net](https://potplayer.daum.net/) | `winget install Daum.PotPlayer` |

## Communication and Meetings

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| QQ | Tencent instant messenger with file transfer and group chat. | [im.qq.com](https://im.qq.com/) | `winget install Tencent.QQ.NT` |
| WeChat | Tencent messaging, payment and mini-program client. | [weixin.qq.com](https://weixin.qq.com/) | `winget install Tencent.WeChat.Universal` |
| WeLink | Huawei Cloud enterprise collaboration and video conferencing client. | [huaweicloud.com](https://www.huaweicloud.com/product/welink.html) | `winget install Huawei.Welink` |

## Science and Personal Data

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| QGIS | Open-source geographic information system for viewing and analysing spatial data. | [qgis.org](https://qgis.org/) | `winget install OSGeo.QGIS` |
| LifeLog | Local-first personal life log with tags, full-text search and Markdown or Excel export. | [github.com/Zzz210s](https://github.com/Zzz210s/LifeLog) | Manual install |

## AI Tools

Tools that support AI coding workflows on this machine.

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| CC Switch | Cross-platform manager that switches provider configs for Claude Code, Codex and other AI CLI agents. | [github.com/farion1231](https://github.com/farion1231/cc-switch) | `winget install farion1231.CC-Switch` |
| CCTO | Claude Code Token Optimizer: cuts token usage with local semantic indexing and MCP tools. | [github.com/alidhibi](https://github.com/alidhibi/ccto) | `npm install -g @alidhibi/ccto` |
| Chrome DevTools MCP | MCP server that lets AI agents inspect and drive Chrome DevTools. | [github.com/ChromeDevTools](https://github.com/ChromeDevTools/chrome-devtools-mcp) | `npm install -g chrome-devtools-mcp` |
| OpenCommit | Generates git commit messages with an LLM from the staged diff. | [github.com/di-sukharev](https://github.com/di-sukharev/opencommit) | `npm install -g opencommit` |

## LLM Clients and Front-ends

Clients and command-line front-ends for large language models.

| Software | Introduction | Official site | Install command |
|---|---|---|---|
| Claude Code | Anthropic's terminal coding agent for Claude models. | [github.com/anthropics](https://github.com/anthropics/claude-code) | `winget install Anthropic.ClaudeCode` |
| OpenCode Desktop | Desktop client for the OpenCode AI coding agent. | [opencode.ai](https://opencode.ai/) | `winget install SST.OpenCodeDesktop` |
| pi | Coding agent CLI with read, bash, edit and write tools plus session management. | [github.com/earendil-works](https://github.com/earendil-works/pi) | `npm install -g @earendil-works/pi-coding-agent` |

## Scope and Method

Compiled on 2026-09-15 from two sources on my Windows machine:

- the top level of the `E:\` software drive;
- system-wide and user-local development tools under `C:\Program Files`, `C:\Program Files (x86)` and `%LOCALAPPDATA%\Programs`.

Entries are grouped by what a program does, following the taxonomy that community software lists use. The install command column states how each entry can be installed: `winget install`, `npm install -g`, or "Manual install" when the program has to come from its official page.

Every winget package identifier was confirmed against the winget source before it was written down. Entries without a public homepage are linked to their official repository instead.

Windows system folders, build output directories and dependency-only packages are left out: `$RECYCLE.BIN`, `Config.Msi`, `System Volume Information`, `0-cargo-target` and the `cacert` certificate bundle.

Every link was opened and checked for reachability while writing this list.

## License

[MIT](LICENSE)
