# 软件清单(Windows)

[English](README.md) | 简体中文

本机(Windows)已安装软件的分类清单,每条含简要介绍与官网或官方仓库链接。

## 目录

- [Windows 下载与安装](#windows-下载与安装)
- [Scoop 安装](#scoop-安装)
- [pnpm 安装](#pnpm-安装)
- [包管理器与统一管理](#包管理器与统一管理)
- [开发工具](#开发工具)
  - [IDE 与编辑器](#ide-与编辑器)
  - [运行时与包管理](#运行时与包管理)
  - [终端与命令行](#终端与命令行)
  - [构建与容器](#构建与容器)
- [系统与效率](#系统与效率)
  - [系统维护与清理](#系统维护与清理)
  - [文件与压缩](#文件与压缩)
  - [剪贴板与截图](#剪贴板与截图)
  - [自动化](#自动化)
- [文档与办公](#文档与办公)
- [网络与云](#网络与云)
  - [浏览器](#浏览器)
  - [代理与加速](#代理与加速)
  - [云盘与同步](#云盘与同步)
- [媒体与图像](#媒体与图像)
- [沟通与会议](#沟通与会议)
- [科学与个人数据](#科学与个人数据)
- [AI 工具](#ai-工具)
- [LLM 客户端与操作端](#llm-客户端与操作端)
- [Windows 设置](#windows-设置)
- [环境配置](#环境配置)
- [许可](#许可)

## Windows 下载与安装

微软官方的 Windows 下载与安装页面:

| 教程 | 介绍 | 链接 |
|---|---|---|
| 下载 Windows 11 | 官方页面,含 Windows 11 安装助手、媒体创建工具与 ISO 下载。 | [microsoft.com](https://www.microsoft.com/zh-cn/software-download/windows11) |
| 安装 Windows 11 的方法 | 微软支持文档,涵盖升级安装、全新安装与安装介质等方案。 | [support.microsoft.com](https://support.microsoft.com/zh-cn/windows/deployment/install-upgrade/ways-to-install-windows-11) |
| 创建 Windows 安装介质 | 微软支持文档,讲解如何制作可启动 U 盘或 ISO 文件。 | [support.microsoft.com](https://support.microsoft.com/zh-cn/windows/deployment/install-upgrade/create-installation-media-for-windows) |

## Scoop 安装

Scoop 是 Windows 上的命令行安装器:免管理员权限,程序统一装在 `~\scoop`,并通过 shim 暴露可执行文件。

- 官网: [scoop.sh](https://scoop.sh/)

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

非 main bucket 的条目需先执行 `scoop bucket add extras`、`scoop bucket add java`。

## pnpm 安装

pnpm 是快速且节省磁盘空间的 Node.js 包管理器,本清单用它安装全局命令行工具。

- 官网: [pnpm.io](https://pnpm.io/)

```powershell
Invoke-WebRequest https://get.pnpm.io/install.ps1 -UseBasicParsing | Invoke-Expression
```

应用统一走 **UniGetUI**;运行时、SDK 与命令行工具来自 Scoop 或 WinGet。安装命令列标注的是该条目实际归属的管理器。

## 包管理器与统一管理

应用统一通过 **[UniGetUI](https://github.com/marticliment/UniGetUI)** 管理 —— 它是一个图形界面,背后同时驱动多个包管理器。SDK、运行时与命令行工具仍归 Scoop;凡是带图形安装程序的应用都走 UniGetUI。

- 官网:[marticliment.com/unigetui](https://marticliment.com/unigetui/)

| 后端 | 在本机的角色 | 说明 |
|---|---|---|
| Chocolatey | 机器级安装的应用 | 通过 UniGetUI 调用;`choco` 本身不在 `PATH` 里 |
| Scoop | SDK、运行时、命令行工具 | 从命令行安装与升级 |
| WinGet | 有官方清单的应用 | 通过 UniGetUI 调用,不直接手敲 |
| pip | Python 包 | 由 Scoop 安装的 Python 提供 |
| npm | Node.js 全局命令行工具 | |
| Cargo | Rust 二进制 | 有预编译产物时由 `cargo-binstall` 直接拉取 |
| PowerShell Gallery | PowerShell 模块 | |

### 软件清单备份

UniGetUI 会写出一份 `.ubundle` 文件,列出所有可管理的软件包 —— 这是重装本机的依据:

- 在 **设置 -> 备份** 里启用:本地备份带时间戳,保留最近 5 份。
- 产物位置:`%USERPROFILE%\Documents\UniGetUI\`,每次运行生成一个 `.ubundle`,约 230 个包。
- 恢复方式:把该文件作为启动参数传给 UniGetUI,或在它的 bundle 页面导入。
- UniGetUI 管不了的包(Steam 游戏、Microsoft Store 应用、本地安装程序)会在同一文件里单独列出。

```powershell
# 查看当前备份里都有什么
Get-Content "$env:USERPROFILE\Documents\UniGetUI\*.ubundle" | ConvertFrom-Json |
  Select-Object -ExpandProperty packages | Group-Object ManagerName | Sort-Object Count -Descending
```

## 开发工具

### IDE 与编辑器

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Android Studio | 基于 IntelliJ IDEA 的官方安卓应用开发 IDE。 | [developer.android.com](https://developer.android.com/studio) | `scoop install android-studio`  (extras) |
| IntelliJ IDEA | JetBrains 面向 JVM 语言的 IDE;本机装的是 Ultimate 版,由 WinGet 管理。 | [jetbrains.com/idea](https://www.jetbrains.com/idea/) | `winget install JetBrains.IntelliJIDEA.Ultimate` |
| Microsoft VS Code | 可扩展的代码编辑器,内置 Git、调试器与扩展体系。 | [code.visualstudio.com](https://code.visualstudio.com/) | `winget install Microsoft.VisualStudioCode` |
| 微信web开发者工具 | 开发微信小程序与公众号的官方 IDE。 | [developers.weixin.qq.com](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) | `winget install Tencent.WeixinDevTools` |
| WebStorm | JetBrains 面向 JavaScript 与 TypeScript 的 IDE。 | [jetbrains.com/webstorm](https://www.jetbrains.com/webstorm/) | `winget install JetBrains.WebStorm` |

### 运行时与包管理

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| MinGW-Builds(GCC) | 由 MinGW-w64 源码构建的 Windows 平台 GCC C/C++ 工具链。 | [github.com/niXman](https://github.com/niXman/mingw-builds-binaries) | `scoop install mingw` |
| Node.js | 用于工具链与服务端代码的 JavaScript 运行时。 | [nodejs.org](https://nodejs.org/) | `scoop install nodejs-lts` |
| Oracle JDK 26 | Oracle 官方发布的 Java 26;为需要它的项目保留。 | [oracle.com/java](https://www.oracle.com/java/technologies/downloads/) | `winget install Oracle.JDK.26` |
| Temurin 21 (LTS) | Eclipse Temurin 发布的 OpenJDK 21;命令行 `java` 默认指向它。 | [adoptium.net](https://adoptium.net/) | `scoop install temurin21-jdk`  (java) |
| pnpm | 快速且节省磁盘空间的 Node.js 包管理器。 | [pnpm.io](https://pnpm.io/) | `scoop install pnpm` |
| Python | 通用编程语言与解释器。 | [python.org](https://www.python.org/) | `scoop install python` |
| Rust(rustup) | Rust 语言工具链安装器与版本管理器。 | [rust-lang.org](https://www.rust-lang.org/) | `scoop install rustup` |

### 终端与命令行

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| bat | 带语法高亮与 Git 集成的 cat 替代品。 | [github.com/sharkdp](https://github.com/sharkdp/bat) | `scoop install bat` |
| cmder | 内置 ConEmu 与 Clink 的便携控制台模拟器。 | [cmder.net](https://cmder.net/) | `choco install cmder` |
| Dark(WiX) | WiX 工具集中的 Windows 安装包反编译器。 | [wixtoolset.org](https://wixtoolset.org/) | `scoop install dark` |
| fd | 快速且更易用的 find 替代品。 | [github.com/sharkdp](https://github.com/sharkdp/fd) | `scoop install fd` |
| Git | 分布式版本控制系统。改由 Scoop 管理:WinGet 那份无法更新 —— 它的安装器只要检测到 git-bash 进程在运行就拒绝继续(pi 的 shell 就是其中之一)。 | [git-scm.com](https://git-scm.com/) | `scoop install git` |
| GitHub CLI | GitHub 官方命令行客户端。 | [cli.github.com](https://cli.github.com/) | `scoop install gh` |
| Helix | 内置语言服务器支持的模态文本编辑器。 | [helix-editor.com](https://helix-editor.com/) | `scoop install helix` |
| jq | 命令行 JSON 处理工具。 | [jqlang.github.io](https://jqlang.github.io/jq/) | `scoop install jq` |
| Make | GNU 构建自动化工具。 | [gnu.org/software/make](https://www.gnu.org/software/make/) | `scoop install make` |
| ripgrep | 遵循 gitignore 规则的递归搜索工具。 | [github.com/BurntSushi](https://github.com/BurntSushi/ripgrep) | `scoop install ripgrep` |
| wget | 通过 HTTP、HTTPS、FTP 下载文件的命令行工具。 | [gnu.org/software/wget](https://www.gnu.org/software/wget/) | `scoop install wget` |
| Xshell | Windows 上的 SSH / Telnet 终端客户端,家庭版免费。 | [xshell.com](https://www.xshell.com/) | 手动安装 |

### 构建与容器

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Docker Desktop | 在 Windows 上构建与运行 Linux 容器的容器平台。 | [docker.com](https://www.docker.com/) | `winget install Docker.DockerDesktop` |
| Microsoft Visual Studio Build Tools 2026 | 用于构建 C++ 项目的 MSVC 编译器、链接器与 Windows SDK 工具链。 | [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/) | 手动安装 |

## 系统与效率

### 系统维护与清理

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| BleachBit | 跨平台磁盘与隐私清理工具,可清除缓存、日志与使用记录。 | [bleachbit.org](https://www.bleachbit.org/) | `scoop install bleachbit`  (extras) |
| ContextMenuManager | 管理 Windows 右键菜单项的便携工具。 | [github.com/BluePointLilac](https://github.com/BluePointLilac/ContextMenuManager) | `winget install BluePointLilac.ContextMenuManager` |
| Dism++ | 基于 DISM 的便携系统维护与清理工具。 | [github.com/Chuyu-Team](https://github.com/Chuyu-Team/Dism-Multi-language) | `scoop install dismplusplus`  (extras) |
| Geek Uninstaller | 便携卸载工具,可一并清除残留文件与注册表项。 | [geekuninstaller.com](https://geekuninstaller.com/) | `scoop install geekuninstaller`  (extras) |
| LightC | 轻量 C 盘清理工具,覆盖垃圾清理、大文件、系统瘦身与卸载残留。 | [github.com/Chunyu33](https://github.com/Chunyu33/light-c) | 手动安装 |
| Mem Reduct | 轻量内存实时监控工具,占用超过阈值时自动修剪工作集。 | [github.com/henrypp](https://github.com/henrypp/memreduct) | `choco install memreduct` |
| SpaceSniffer | 以矩形树图展示磁盘空间占用。 | [uderzo.it](http://www.uderzo.it/main_products/space_sniffer/) | `scoop install spacesniffer`  (extras) |
| Viap | 通过 NTFS junction 把已安装应用及其数据迁移到其他磁盘。 | [github.com/Chunyu33](https://github.com/Chunyu33/viap) | 手动安装 |

### 文件与压缩

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| 7-Zip | 高压缩比、界面简洁的文件压缩软件。 | [7-zip.org](https://www.7-zip.org/) | `scoop install 7zip` |
| Bandizip | 支持 ZIP、7Z、RAR 等格式的快速压缩软件。要求使用 6.25 版,winget 与 scoop 均未提供该版本,故手动安装。 | [bandisoft.com](https://www.bandisoft.com/bandizip/) | 手动安装(6.25 版) |
| Q-Dir | 四窗格文件管理器,支持标签页与快速筛选视图。 | [q-dir.com](https://www.q-dir.com/) | `scoop install q-dir`  (extras) |

### 剪贴板与截图

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Ditto | 开源剪贴板历史管理工具,支持搜索历史条目。 | [github.com/sabrogden](https://github.com/sabrogden/Ditto) | `scoop install ditto`  (extras) |
| PixPin | 集截图、贴图、长截图、OCR 与录屏于一体的工具。 | [pixpin.com](https://pixpin.com/) | `winget install PixPin.PixPin` |

### 自动化

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| AutoHotkey | Windows 自动化脚本语言,用于编写热键与自动操作。 | [autohotkey.com](https://www.autohotkey.com/) | `scoop install autohotkey`  (extras) |
| Autovisor | 基于 Playwright 的网课自动播放脚本。 | [github.com/CXRunfree](https://github.com/CXRunfree/Autovisor) | 手动安装 |
| Microsoft Rewards Script | 基于 TypeScript 与 Playwright 的 Microsoft Rewards 每日任务自动化脚本。 | [github.com/TheNetsky](https://github.com/TheNetsky/Microsoft-Rewards-Script) | 手动安装 |

## 文档与办公

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| AnyTXT Searcher | 本地文档全文搜索引擎。 | [anytxt.net](https://anytxt.net/) | `winget install AnyTXT.AnyTXTSearcher` |
| PDF24 Creator | 免费的离线 PDF 工具箱,可创建、合并、压缩与编辑。 | [pdf24.org](https://www.pdf24.org/en/) | `winget install geeksoftwareGmbH.PDF24Creator` |
| WPS Office | 含文字、表格、演示与 PDF 的办公套件。 | [wps.com](https://www.wps.com/) | `scoop install wpsoffice`  (extras) |

## 网络与云

### 浏览器

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Google Chrome | 谷歌浏览器,支持账号同步、扩展与站点隔离。 | [google.com/chrome](https://www.google.com/chrome/) | `scoop install googlechrome` |

### 代理与加速

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Throne | 基于 sing-box 的代理客户端,NekoRay 的后继项目,支持 VLESS、Hysteria、TUIC 等协议。 | [github.com/throneproj](https://github.com/throneproj/Throne) | `scoop install throne` |
| Watt Toolkit(Steam++) | 面向 Steam、GitHub 等服务的网络加速与脚本工具箱。 | [steampp.net](https://steampp.net/) | 手动安装 |

### 云盘与同步

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| 百度网盘(Baidu Netdisk) | 百度云存储客户端。 | [pan.baidu.com](https://pan.baidu.com/) | `winget install Baidu.BaiduNetdisk` |
| 夸克网盘(Quark Cloud Drive) | 夸克云存储桌面客户端。 | [pan.quark.cn](https://pan.quark.cn/) | `winget install Alibaba.QuarkCloudDrive` |

## 媒体与图像

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Affinity | Canva 旗下的专业设计套件,覆盖照片编辑、矢量设计与排版。 | [affinity.studio](https://www.affinity.studio/) | `winget install Canva.Affinity` |
| DaVinci Resolve | 集剪辑、调色、特效与音频后期于一体的专业视频软件。 | [blackmagicdesign.com](https://www.blackmagicdesign.com/products/davinciresolve) | 手动安装 |
| NetEase Cloud Music(网易云音乐) | 带个性化推荐与社交功能的音乐客户端。 | [music.163.com](https://music.163.com/) | `winget install NetEase.CloudMusic` |
| OBS Studio | 开源直播与录屏软件。 | [obsproject.com](https://obsproject.com/) | `scoop install obs-studio`  (extras) |
| PotPlayer | Daum 出品、功能丰富的全能播放器。 | [potplayer.daum.net](https://potplayer.daum.net/) | `scoop install potplayer`  (extras) |

## 沟通与会议

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| 手机连接(Phone Link) | 微软应用,把 Android 或 iPhone 连接到 Windows,在电脑上收发消息、接打电话与查看照片。 | [microsoft.com](https://www.microsoft.com/zh-cn/windows/sync-across-your-devices) | `winget install 9NMPJ99VJBWV` |
| QQ | 腾讯即时通讯客户端,支持文件传输与群聊。 | [im.qq.com](https://im.qq.com/) | `scoop install qq`  (extras) |
| WeChat(微信) | 腾讯的即时通讯客户端,支持支付与小程序。 | [weixin.qq.com](https://weixin.qq.com/) | `scoop install wechat`  (extras) |
| WeLink | 华为云企业协同办公与视频会议客户端。 | [huaweicloud.com](https://www.huaweicloud.com/product/welink.html) | `winget install Huawei.Welink` |

## 科学与个人数据

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| QGIS | 开源地理信息系统,用于查看与分析空间数据。 | [qgis.org](https://qgis.org/) | `winget install OSGeo.QGIS` |
| LifeLog | 本地优先的个人生活记录库,支持标签、全文搜索与 Markdown / Excel 导出。 | [github.com/Zzz210s](https://github.com/Zzz210s/LifeLog) | 手动安装 |

## AI 工具

本机用于支撑 AI 编码流程的工具。

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| CC Switch | 切换 Claude Code、Codex 等 AI CLI 供应商配置的跨平台桌面工具。 | [github.com/farion1231](https://github.com/farion1231/cc-switch) | `scoop install cc-switch`  (extras) |

## LLM 客户端与操作端

使用大语言模型的客户端与命令行操作端。

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Claude Code | Anthropic 官方面向 Claude 模型的终端编程代理。 | [github.com/anthropics](https://github.com/anthropics/claude-code) | `pnpm add -g @anthropic-ai/claude-code` |
| OpenCode Desktop | OpenCode AI 编程助手的桌面客户端。 | [opencode.ai](https://opencode.ai/) | `scoop install opencode-desktop`  (extras) |
| pi | 带 read、bash、edit、write 工具与会话管理的编程代理 CLI。 | [github.com/earendil-works](https://github.com/earendil-works/pi) | `pnpm add -g @earendil-works/pi-coding-agent` |
| Zed | 用 Rust 编写的高性能代码编辑器。 | [zed.dev](https://zed.dev/) | `scoop install zed`  (extras) |

## Windows 设置

本机检测到的设置(Windows 11 专业版,build 26200):

| 设置项 | 当前状态 | 说明 |
|---|---|---|
| 自动关机 | 计划任务 `AutoShutdown0400`,每日 04:00 | 执行 `E:\Microsoft-Rewards-Script-4.3.2\scripts\windows\run-shutdown.vbs`;2026-09-24 最近一次执行成功 |
| 快速启动 | 已启用(`HiberbootEnabled=1`) | 关机为混合关机 |
| 长路径支持 | 已启用(`LongPathsEnabled=1`) | 允许超过 260 字符的路径,Scoop 与 Git 目录依赖此设置 |
| 睡眠与休眠 | 仅支持 S0 低电量待机;S1-S3 与休眠不可用 | `powercfg /a` 结果 |
| 开发者模式 | 未启用 | |
| WSL | 默认版本 2 | 发行版:`docker-desktop`、`FedoraLinux-44`、`Ubuntu-26.04` |
| 分页文件 | 系统管理,`C:\pagefile.sys` 24 GB | 物理内存 16 GB,峰值使用 4.9 GB |
| 自定义计划任务 | `AutoShutdown0400`、`MemReduct-Elevated`、`MicrosoftRewardsScript`、`Throne AutoRun`、`iGoAudioTaskSession`、`QuickClipboardAdmin`、开机自动挂载 E 盘、WPS 两项 | 其余任务均为 Windows 自带 |

## 环境配置

各条目需要的环境变量与配置,取值均为本机当前状态。

| 程序 | 需要配置的内容 | 本机当前状态 |
|---|---|---|
| Oracle JDK 26 | 手动安装位置 | `C:\Program Files\Java\jdk-26`;它的 `javapath` 条目已从机器级 `PATH` 移除,不再遮蔽默认 JDK |
| Temurin 21 (LTS) | `JAVA_HOME`、`PATH` | 用户级 `JAVA_HOME` 与 `PATH` 上的 `java`/`javac` 都指向 `%USERPROFILE%\scoop\apps\temurin21-jdk\current`,命令行与 Gradle 保持一致 |
| Python | `PATH`(scoop shims 与 `Scripts`)、pip 源 | scoop 安装的 3.14.6;两个目录都在用户 PATH;未配置 pip 镜像 |
| Rust (rustup) | 把 `%USERPROFILE%\.cargo\bin` 加入 `PATH` | 已加入;rustc 1.98.1;未覆盖 `CARGO_HOME`/`RUSTUP_HOME` |
| Node.js | `PATH`、npm prefix、`NODE_OPTIONS` | v24.14.0;`C:\Program Files\nodejs` 在机器级 PATH;npm prefix 为 `%APPDATA%\npm`;`NODE_OPTIONS=--max-old-space-size=1536` |
| pnpm | `PNPM_HOME` 与 `PATH`、store 目录 | `PNPM_HOME=%LOCALAPPDATA%\pnpm`,已在用户 PATH;store 已迁到 `E:\node_modules\.pnpm-store\v11` |
| Git | 身份、凭据助手、换行、PATH 顺序 | `user.name=Zzz210s`;GitHub 与 Gist 凭据通过 URL 级 helper 交给 gh,系统级为 manager;未设 `core.autocrlf`。当前生效的是 Scoop 那份(`2.56.0`):用户 `PATH` 里 `%USERPROFILE%\scoop\shims` 排在残留的 `C:\Program Files\Git\...` 之前,机器级 `PATH` 已不再引用 WinGet 的安装 |
| Scoop | 安装根目录、bucket | 默认根目录 `%USERPROFILE%\scoop`;bucket 为 `main`、`extras`、`java` |
| IntelliJ IDEA、WebStorm | 启动器的 VM 选项 | `IDEA_VM_OPTIONS` 等 JetBrains 变量指向 `E:\0-IntelliJ IDEA 2025.1.2\win2021-2025\vmoptions\*.vmoptions`,用户级与机器级均已设置 |
| Android Studio | Android SDK | SDK 在 `%LOCALAPPDATA%\Android\Sdk`,`platform-tools` 在机器 PATH;未设 `ANDROID_HOME` |
| MinGW-Builds (GCC) | 把 `C:\MinGW\bin` 加到 `PATH` | 已加入 |
| Docker Desktop | WSL 2 后端 | WSL 默认版本 2,存在 `docker-desktop` 发行版;`...\Docker\resources\bin` 在机器 PATH |
| cmder | `CMDER_ROOT`、`ConEmuDir` | 都指向 Chocolatey 安装目录 `C:\tools\Cmder` |
| Mem Reduct | 需提权计划任务 | 由 Chocolatey 安装;`MemReduct-Elevated` 以最高权限运行,因为自动清理需要提权。阈值 93% |
| LightC、Viap | 管理员权限 | 清理与 junction 迁移都需要管理员会话 |
| Throne | 管理员权限、路由模式 | 计划任务 `Throne AutoRun`;TUN 模式需要提权 |
| AnyTXT Searcher | 索引服务 | `ATService` 已禁用,需要时手动启动 |
| VS Code、Zed、Xshell | `PATH`(可选) | VS Code `E:\0-Microsoft VS Code\bin` 与 Zed `%LOCALAPPDATA%\Programs\Zed\bin` 在用户 PATH;Xshell 在机器级 PATH |
| cargo-binstall | 解析器使用的 DNS | 它读默认网卡的 DNS 列表而不是系统解析器。WLAN 网卡已设为 `172.19.0.2`(Throne 的 TUN DNS,本机唯一可用的),并以 `223.5.5.5` 作为备选 |
| 用户 `PATH` | 失效条目 | 已删除 15 个指向已移除软件的条目(Scoop 时期的 3 个 cmder 残留、旧 Bandizip 路径、Ollama、9 个轮换后的 Claude 插件缓存路径);41 -> 26 条 |

## 许可

[MIT](LICENSE)
