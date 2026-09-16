# 软件清单(Windows)

[English](README.md) | 简体中文

本机(Windows)已安装软件的分类清单,每条含简要介绍与官网或官方仓库链接。

## Windows 安装官方教程

微软官方的 Windows 下载与安装页面:

| 教程 | 介绍 | 链接 |
|---|---|---|
| 下载 Windows 11 | 官方页面,含 Windows 11 安装助手、媒体创建工具与 ISO 下载。 | [microsoft.com](https://www.microsoft.com/zh-cn/software-download/windows11) |
| 安装 Windows 11 的方法 | 微软支持文档,涵盖升级安装、全新安装与安装介质等方案。 | [support.microsoft.com](https://support.microsoft.com/zh-cn/windows/deployment/install-upgrade/ways-to-install-windows-11) |
| 创建 Windows 安装介质 | 微软支持文档,讲解如何制作可启动 U 盘或 ISO 文件。 | [support.microsoft.com](https://support.microsoft.com/zh-cn/windows/deployment/install-upgrade/create-installation-media-for-windows) |

## 目录

- [Windows 安装官方教程](#windows-安装官方教程)
- [可 Scoop 安装管理](#可-scoop-安装管理)
- [单独安装管理](#单独安装管理)
- [AI 工具](#ai-工具)
- [LLM 客户端与操作端](#llm-客户端与操作端)
- [范围与整理方法](#范围与整理方法)
- [许可](#许可)

## 可 Scoop 安装管理

**Scoop** 是 Windows 上的命令行安装器:它以非管理员权限把程序装进 `~\scoop`,通过 shim 暴露可执行文件,升级与卸载都在一处完成。

- 官网:[scoop.sh](https://scoop.sh/)
- 安装 Scoop(在 PowerShell 中执行):

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```

下表"安装命令"列使用程序所在 bucket 的 manifest 名。安装 extras / java bucket 中的程序前,先各添加一次:`scoop bucket add extras`、`scoop bucket add java`。

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| 7-Zip | 高压缩比、界面简洁的文件压缩软件。 | [7-zip.org](https://www.7-zip.org/) | `scoop install 7zip` |
| Android Studio | 基于 IntelliJ IDEA 的官方安卓应用开发 IDE。 | [developer.android.com](https://developer.android.com/studio) | `scoop install android-studio` |
| AutoHotkey | Windows 自动化脚本语言,用于编写热键与自动操作。 | [autohotkey.com](https://www.autohotkey.com/) | `scoop install autohotkey` |
| Bandizip | 支持 ZIP、7Z、RAR 等格式的快速压缩软件。 | [bandisoft.com](https://www.bandisoft.com/bandizip/) | `scoop install bandizip` |
| bat | 带语法高亮与 Git 集成的 cat 替代品。 | [github.com/sharkdp](https://github.com/sharkdp/bat) | `scoop install bat` |
| BleachBit | 跨平台磁盘与隐私清理工具,可清除缓存、日志与使用记录。 | [bleachbit.org](https://www.bleachbit.org/) | `scoop install bleachbit` |
| cmder | 内置 ConEmu 与 Clink 的便携控制台模拟器。 | [cmder.net](https://cmder.net/) | `scoop install cmder` |
| Dark(WiX) | WiX 工具集中的 Windows 安装包反编译器。 | [wixtoolset.org](https://wixtoolset.org/) | `scoop install dark` |
| Dism++ | 基于 DISM 的便携系统维护与清理工具。 | [github.com/Chuyu-Team](https://github.com/Chuyu-Team/Dism-Multi-language) | `scoop install dismplusplus` |
| Ditto | 开源剪贴板历史管理工具,支持搜索历史条目。 | [github.com/sabrogden](https://github.com/sabrogden/Ditto) | `scoop install ditto` |
| Eclipse Temurin JDK 21 | Adoptium 项目维护的免费 OpenJDK 21(LTS)发行版。 | [adoptium.net](https://adoptium.net/) | `scoop install temurin21-jdk` |
| fd | 快速且更易用的 find 替代品。 | [github.com/sharkdp](https://github.com/sharkdp/fd) | `scoop install fd` |
| Geek Uninstaller | 便携卸载工具,可一并清除残留文件与注册表项。 | [geekuninstaller.com](https://geekuninstaller.com/) | `scoop install geekuninstaller` |
| Git | 分布式版本控制系统。 | [git-scm.com](https://git-scm.com/) | `scoop install git` |
| GitHub CLI | GitHub 官方命令行客户端。 | [cli.github.com](https://cli.github.com/) | `scoop install gh` |
| Helix | 内置语言服务器支持的模态文本编辑器。 | [helix-editor.com](https://helix-editor.com/) | `scoop install helix` |
| IntelliJ IDEA | JetBrains 出品的 JVM 语言 IDE,manifest 安装免费的社区版。 | [jetbrains.com/idea](https://www.jetbrains.com/idea/) | `scoop install idea` |
| jq | 命令行 JSON 处理工具。 | [jqlang.github.io](https://jqlang.github.io/jq/) | `scoop install jq` |
| Make | GNU 构建自动化工具。 | [gnu.org/software/make](https://www.gnu.org/software/make/) | `scoop install make` |
| Microsoft Visual C++ Redistributable | MSVC 编译程序所需的运行库。 | [learn.microsoft.com](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) | `scoop install vcredist2022` |
| Microsoft VS Code | 可扩展的代码编辑器,内置 Git、调试器与扩展市场。 | [code.visualstudio.com](https://code.visualstudio.com/) | `scoop install vscode` |
| NekoBox(NekoRay) | 基于 sing-box 的 Qt 代理客户端,上游仓库已归档停止维护。 | [github.com/MatsuriDayo](https://github.com/MatsuriDayo/nekoray) | `scoop install nekobox` |
| Node.js | 用于工具链与服务端开发的 JavaScript 运行时。 | [nodejs.org](https://nodejs.org/) | `scoop install nodejs` |
| OBS Studio | 开源直播与录屏软件。 | [obsproject.com](https://obsproject.com/) | `scoop install obs-studio` |
| Oracle JDK 26 | Oracle 官方的 Java 26 OpenJDK 发行版。 | [oracle.com/java](https://www.oracle.com/java/technologies/downloads/) | `scoop install oraclejdk` |
| pnpm | 快速且节省磁盘空间的 Node.js 包管理器。 | [pnpm.io](https://pnpm.io/) | `scoop install pnpm` |
| PotPlayer | Daum 出品、功能丰富的全能播放器。 | [potplayer.daum.net](https://potplayer.daum.net/) | `scoop install potplayer` |
| Python | 通用编程语言与解释器。 | [python.org](https://www.python.org/) | `scoop install python` |
| Q-Dir | 四窗格文件管理器,支持标签页与快速筛选视图。 | [q-dir.com](https://www.q-dir.com/) | `scoop install q-dir` |
| QQ | 腾讯即时通讯客户端,支持文件传输与群聊。 | [im.qq.com](https://im.qq.com/) | `scoop install qq` |
| ripgrep | 遵循 gitignore 规则的递归搜索工具。 | [github.com/BurntSushi](https://github.com/BurntSushi/ripgrep) | `scoop install ripgrep` |
| Rust(rustup) | Rust 语言工具链安装器与版本管理器。 | [rust-lang.org](https://www.rust-lang.org/) | `scoop install rustup` |
| SpaceSniffer | 以矩形树图展示磁盘空间占用。 | [uderzo.it](http://www.uderzo.it/main_products/space_sniffer/) | `scoop install spacesniffer` |
| Typora | 极简 Markdown 编辑器,实时预览并支持导出。 | [typora.io](https://typora.io/) | `scoop install typora` |
| WeChat(微信) | 腾讯的即时通讯客户端,支持支付与小程序。 | [weixin.qq.com](https://weixin.qq.com/) | `scoop install wechat` |
| WebStorm | JetBrains 出品的 JavaScript / TypeScript IDE。 | [jetbrains.com/webstorm](https://www.jetbrains.com/webstorm/) | `scoop install webstorm` |
| wget | 通过 HTTP、HTTPS、FTP 下载文件的命令行工具。 | [gnu.org/software/wget](https://www.gnu.org/software/wget/) | `scoop install wget` |
| WPS Office | 含文字、表格、演示与 PDF 的办公套件。 | [wps.com](https://www.wps.com/) | `scoop install wpsoffice` |
| Zed | 用 Rust 编写的高性能代码编辑器。 | [zed.dev](https://zed.dev/) | `scoop install zed` |

## 单独安装管理

以下程序没有 Scoop manifest,需按官网页面手动安装:

| 软件 | 介绍 | 官网 |
|---|---|---|
| AnyTXT Searcher | 本地文档全文搜索引擎。 | [anytxt.net](https://anytxt.net/) |
| Autovisor | 基于 Playwright 的网课自动播放脚本。 | [github.com/CXRunfree](https://github.com/CXRunfree/Autovisor) |
| 百度网盘(Baidu Netdisk) | 百度云存储客户端。 | [pan.baidu.com](https://pan.baidu.com/) |
| ContextMenuManager | 管理 Windows 右键菜单项的便携工具。 | [github.com/BluePointLilac](https://github.com/BluePointLilac/ContextMenuManager) |
| DaVinci Resolve | 集剪辑、调色、特效与音频后期于一体的专业视频软件。 | [blackmagicdesign.com](https://www.blackmagicdesign.com/products/davinciresolve) |
| Docker Desktop | 在 Windows 上构建与运行 Linux 容器的容器平台。 | [docker.com](https://www.docker.com/) |
| LifeLog | 本地优先的个人生活记录库,支持标签、全文搜索与 Markdown / Excel 导出。 | [github.com/Zzz210s](https://github.com/Zzz210s/LifeLog) |
| Microsoft Rewards Script | 基于 TypeScript 与 Playwright 的 Microsoft Rewards 每日任务自动化脚本。 | [github.com/TheNetsky](https://github.com/TheNetsky/Microsoft-Rewards-Script) |
| Microsoft Visual Studio Build Tools 2026 | 用于构建 C++ 项目的 MSVC 编译器、链接器与 Windows SDK 工具链。 | [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/) |
| MinGW-Builds(GCC) | 基于 MinGW-w64 源码构建的 Windows 平台 GCC C/C++ 工具链。 | [github.com/niXman](https://github.com/niXman/mingw-builds-binaries) |
| NetEase Cloud Music(网易云音乐) | 带个性化推荐与社交功能的音乐客户端。 | [music.163.com](https://music.163.com/) |
| PDF24 Creator | 免费的离线 PDF 工具箱,可创建、合并、压缩与编辑。 | [pdf24.org](https://www.pdf24.org/en/) |
| pineapple-pictures | 基于 Qt 的轻量图片查看器,含基础编辑。 | [github.com/BLumia](https://github.com/BLumia/pineapple-pictures) |
| PixPin | 集截图、贴图、长截图、OCR 与录屏于一体的工具。 | [pixpin.com](https://pixpin.com/) |
| QGIS | 开源地理信息系统,用于查看与分析空间数据。 | [qgis.org](https://qgis.org/) |
| 夸克网盘(Quark Cloud Drive) | 夸克云存储桌面客户端。 | [pan.quark.cn](https://pan.quark.cn/) |
| Watt Toolkit(Steam++) | 面向 Steam、GitHub 等服务的网络加速与脚本工具箱。 | [steampp.net](https://steampp.net/) |
| 微信web开发者工具 | 开发微信小程序与公众号的官方 IDE。 | [developers.weixin.qq.com](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html) |
| WeLink | 华为云企业协同办公与视频会议客户端。 | [huaweicloud.com](https://www.huaweicloud.com/product/welink.html) |
| Xshell | Windows 上的 SSH / Telnet 终端客户端,家庭版免费。 | [xshell.com](https://www.xshell.com/) |

## AI 工具

本机用于支撑 AI 编码流程的工具:

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| CC Switch | 切换 Claude Code、Codex 等 AI CLI 供应商配置的跨平台桌面工具。 | [github.com/farion1231](https://github.com/farion1231/cc-switch) | `scoop install cc-switch` |
| CCTO | Claude Code Token 优化器:通过本地语义索引与 MCP 工具降低 token 消耗。 | [github.com/alidhibi](https://github.com/alidhibi/ccto) | `npm install -g @alidhibi/ccto` |
| Chrome DevTools MCP | 让 AI 代理检查与驱动 Chrome DevTools 的 MCP 服务器。 | [github.com/ChromeDevTools](https://github.com/ChromeDevTools/chrome-devtools-mcp) | `npm install -g chrome-devtools-mcp` |
| OpenCommit | 用 LLM 根据暂存区改动生成 git 提交信息。 | [github.com/di-sukharev](https://github.com/di-sukharev/opencommit) | `npm install -g opencommit` |

## LLM 客户端与操作端

使用大语言模型的客户端与命令行操作端:

| 软件 | 介绍 | 官网 | 安装命令 |
|---|---|---|---|
| Claude Code | Anthropic 官方面向 Claude 模型的终端编程代理。 | [github.com/anthropics](https://github.com/anthropics/claude-code) | `scoop install claude-code` |
| OpenCode Desktop | OpenCode AI 编程助手的桌面客户端。 | [opencode.ai](https://opencode.ai/) | `scoop install opencode-desktop` |
| pi | 带 read、bash、edit、write 工具与会话管理的编程代理 CLI。 | [github.com/earendil-works](https://github.com/earendil-works/pi) | `npm install -g @earendil-works/pi-coding-agent` |

## 范围与整理方法

本清单于 2026-09-15 从本机三处来源整理:

- `E:\` 软件盘顶层目录;
- Scoop 安装的包(`scoop list`);
- `C:\Program Files`、`C:\Program Files (x86)`、`%LOCALAPPDATA%\Programs` 下的系统级与用户级开发工具。

按"最适合的安装方式"分组:Scoop 部分给出各程序所属 bucket 的 manifest 名与安装命令,其余程序从官网手动安装,AI 相关程序单列。Scoop manifest 名逐条比对过 `main`、`extras`、`java` 三个 bucket。

Windows 系统目录、构建产物目录与纯依赖包已排除:`$RECYCLE.BIN`、`Config.Msi`、`System Volume Information`、`0-cargo-target`,以及 `cacert` 证书包。

所有链接在整理时都做过可达性检查;没有公开主页的条目改为链接其官方仓库。

## 许可

[MIT](LICENSE)
