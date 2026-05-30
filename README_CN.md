# ![Logo](assets/icon.svg) Ludusavi

Ludusavi 是一款用于备份 PC 视频游戏存档数据的工具，使用 [Rust](https://www.rust-lang.org) 编写。
它具有跨平台特性，并支持多个游戏商店。

## 功能特性

* 能够备份超过 19,000 款游戏的数据以及您自己的自定义条目。
* 支持 Steam、GOG、Epic、Heroic、Lutris 及其他游戏库的备份与恢复。
* 同时提供图形界面（GUI）和用于脚本编写的命令行界面（CLI）。
  支持 Bash、Fish、Zsh、PowerShell 和 Elvish 的 Tab 键自动补全。
* 支持：
  * 以文件形式存储或存储在 Windows 注册表中的存档。
  * Steam 上的 Proton 存档。
  * Steam 截图。
* 提供 [Playnite](https://playnite.link) 扩展：
  https://github.com/mtkennerly/ludusavi-playnite
* 支持在 Steam Deck 上运行。

该工具使用 [Ludusavi Manifest](https://github.com/mtkennerly/ludusavi-manifest) 来获取各游戏的备份信息。
数据主要来源于 [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Home)，
因此，请将任何新增或修正的数据贡献回 Wiki 本身，您的改进也将被纳入 Ludusavi 的数据中。

如果您想帮助将 Ludusavi 翻译成其他语言，请[查看 Crowdin 项目](https://crowdin.com/project/ludusavi)。

## 演示

<!-- 这些锚点保留用于兼容旧的章节标题。 -->
<a name="gui"></a>

> ![GUI 备份预览演示](docs/demo-gui.gif)

## 安装

<!-- 这些锚点保留用于兼容旧的章节标题。 -->
<a name="requirements"></a>
<a name="methods"></a>

从 [发布页面](https://github.com/mtkennerly/ludusavi/releases) 下载适用于 Windows、Linux 或 Mac 的可执行文件。
它是绿色便携的，您可以直接下载并放置在系统的任何位置。

如果您愿意，也可以通过 [Winget、Scoop、Flatpak 和 Cargo](docs/help/installation.md) 安装 Ludusavi。

注意：

* Windows 用户可能会看到“Windows 已保护您的电脑”的弹出窗口，因为 Windows 不识别程序的发布者。请点击“更多信息”，然后选择“仍要运行”来启动程序。
* Mac 用户可能会看到“由于无法验证开发者，Ludusavi 无法打开”的弹出窗口。要允许 Ludusavi 运行，请参考[这篇文章](https://support.apple.com/zh-cn/102445)，特别是“如果您想打开来自未识别开发者的应用……”部分。

## 使用

<!-- 这些锚点保留用于兼容旧的章节标题。 -->
<a name="backup-exclusions"></a>
<a name="backup-retention"></a>
<a name="backup-structure"></a>
<a name="backup-validation"></a>
<a name="cli-api"></a>
<a name="cloud-backup"></a>
<a name="command-line"></a>
<a name="configuration"></a>
<a name="configuration-file"></a>
<a name="custom-games"></a>
<a name="duplicates"></a>
<a name="environment-variables"></a>
<a name="filter"></a>
<a name="game-launch-wrapping"></a>
<a name="logging"></a>
<a name="redirects"></a>
<a name="roots"></a>
<a name="selective-scanning"></a>
<a name="troubleshooting"></a>

针对多个主题提供详细的帮助文档。

### 常规
* [备份自动化](/docs/help/backup-automation.md)
* [备份排除](/docs/help/backup-exclusions.md)
* [备份保留](/docs/help/backup-retention.md)
* [备份验证](/docs/help/backup-validation.md)
* [云备份](/docs/help/cloud-backup.md)
* [自定义游戏](/docs/help/custom-games.md)
* [重复项](/docs/help/duplicates.md)
* [过滤器](/docs/help/filter.md)
* [游戏启动封装](/docs/help/game-launch-wrapping.md)
* [重定向](/docs/help/redirects.md)
* [根目录](/docs/help/roots.md)
* [选择性扫描](/docs/help/selective-scanning.md)
* [跨操作系统转移](/docs/help/transfer-between-operating-systems.md)

### 界面
* [程序文件夹](/docs/help/application-folder.md)
* [备份结构](/docs/help/backup-structure.md)
* [命令行](/docs/help/command-line.md)
* [配置文件](/docs/help/configuration-file.md)
* [环境变量](/docs/help/environment-variables.md)
* [日志记录](/docs/help/logging.md)

### 其他
* [故障排除](/docs/help/troubleshooting.md)
* [如果找不到存档怎么办？](/docs/help/missing-saves.md)

## 社区

社区创建了一些您可能会觉得有用的额外资源。
请注意，这并非详尽列表，且这些项目与 Ludusavi 官方并无隶属关系：

* 次级配置清单（Secondary manifests）：
  * https://github.com/BloodShed-Oni/ludusavi-extra-manifests
  * https://github.com/hblamo/ludusavi-emudeck-manifest
  * https://github.com/hvmzx/ludusavi-manifests
    * 该项目包含一个使用定期 GitHub Workflow 生成清单的示例，该清单为主要清单条目添加了更多路径。
* Steam Deck 上的 Decky Loader 插件：
  * https://github.com/GedasFX/decky-ludusavi
* VS Code 插件：
  * https://marketplace.visualstudio.com/items?itemName=claui.ludusavi
* 工具：
  * https://github.com/jose-l-martins/GSM-to-Ludusavi-converter

## 与其他工具的对比

市面上还有其他优秀的备份工具，但缺少一个单一的跨平台、跨商店解决方案：

* [GameSave Manager](https://www.gamesave-manager.com)（截至 v3.1.512.0）：
  * 仅支持 Windows。
  * 运行速度远慢于 Ludusavi。在相同硬件和默认设置下，GSM 对全系统进行初始扫描需要 2 分钟，而 Ludusavi 仅需 10 秒。扫描后立即执行备份，GSM 需要 4 分 16 秒，而 Ludusavi 仅需 4.5 秒。在本次测试中，GSM 找到了 257 款游戏（2.84 GB），Ludusavi 找到了 297 款游戏（2.95 GiB）。
  * 闭源软件，社区无法贡献改进。
  * 界面可能运行缓慢或无响应。例如，点击“全选/取消全选”时，每个复选框都必须单独切换，对于 257 款游戏，这意味着您最终需要等待约 42 秒。
  * 命令行界面功能极简。
  * 可以为游戏和游戏数据创建符号链接（Symlinks），Ludusavi 目前不支持此功能。
* [Game Backup Monitor](https://mikemaximus.github.io/gbm-web)（截至 v1.2.2）：
  * 不支持 Mac。
  * 数据库仅覆盖 577 款游戏（截至 2022-11-16），不过从 1.3.1 版本开始也可以导入 Ludusavi 的配置清单。
  * 无命令行界面。
  * 可以在游戏结束后自动备份存档。Ludusavi 仅在配合 Playnite 等启动器时才能实现此功能。
* [Gaming Backup Multitool for Linux](https://supremesonicbrazil.gitlab.io/gbml-web)（截至 v1.4.0.0）：
  * 仅支持 Linux 和 Steam。
  * 数据库未积极更新。截至 2022-11-16，最后一次更新是在 2018-06-05。
  * 无命令行界面。

## 开发

请参考 [CONTRIBUTING.md](./CONTRIBUTING.md)。
