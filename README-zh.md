# Awesome NSH

[English](README.md) | 简体中文

收集使用 [Native Shell（NSH）](https://nsh.dev/) 开发的应用，按用途分类，附平台、项目状态及可追溯来源。

NSH 是由 Longbridge 开发的原生 UI 框架，支持以 Rust、TSX 或两者结合编写应用，也可嵌入现有应用。框架支持的平台不等于每个应用实际支持的平台，以下以各项目的说明为准。

**最近核实：2026-11-05。** 当前收录 **20 个应用项目**（包含开发中项目），另列 **4 个演示／原型**。这是一份公开资料清单，不代表已穷尽生态或对应用做过安装测试。

## 目录

- [AI 与开发工具](#ai-与开发工具)
- [笔记与文档](#笔记与文档)
- [系统与安全工具](#系统与安全工具)
- [文件传输与网络](#文件传输与网络)
- [音乐与游戏](#音乐与游戏)
- [教育](#教育)
- [金融与研究](#金融与研究)
- [演示与原型](#演示与原型)
- [官方资源](#官方资源)
- [收录与维护](#收录与维护)

## AI 与开发工具

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| ---------------------- | --------------------------------- | ---------------------------------- | ----------- |
| **Noop** | 在自己的电脑上运行 Claude Code、Codex 团队，处理任务、定时工作和需要人工决策的事项，并从多端查看机器与任务状态。 | macOS、Windows、Linux、iOS、Android、Web；公开源码。 | [官网](https://huacnlee.github.io/noop/) · [源码](https://github.com/huacnlee/noop) · [官方收录](https://nsh.dev/apps/noop/) |
| **Somtus（原 RiWork）** | 集成 Ghostty 终端、tmux 持久会话、项目、Git worktree 与多机 Agent 管理的原生工作台。 | macOS；**Beta**。iOS 客户端正在迁移到 NSH，保留部分原生界面。 | [源码与项目说明](https://github.com/Rhein-Industries/riWork#readme) · [NSH 应用配置](https://github.com/Rhein-Industries/riWork/blob/main/apps/riwork/nsh.json) |
| **callme** | API 客户端，以纯文本 `.http` 文件保存请求；桌面端、CLI 与 MCP 共用请求执行能力，支持响应浏览、环境变量和流式响应。 | 桌面端目前文档提供 macOS 构建方式；源码运行。NSH 用于桌面界面，CLI 和核心库独立于 NSH。 | [源码与 NSH 使用说明](https://github.com/lvwxx/callme#built-with-nsh) · [应用配置](https://github.com/lvwxx/callme/blob/main/app/nsh.json) |
| **Toolbook** | 把 JSON、JWT、正则、HTTP 等工具写成 Markdown 代码块，通过 `$name` 传递数据并自动重算；同一笔记也可由 CLI 或 Agent 执行。 | macOS；已有发布包，v1 界面为中文。 | [官网](https://wenlingang.github.io/toolbook/) · [源码与项目说明](https://github.com/wenlingang/toolbook#readme) |
| **Grok Shell** | 在聊天过程中让模型生成 TSX 模块，编译并热更新为原生交互界面；支持将生成的组件保存为 Mini Apps。 | macOS（AppKit）；源码运行，使用 NSH 分支。 | [源码与技术栈说明](https://github.com/hexuria/grok-shell#tech-stack) |
| **nshde** | 可在运行时扩展自身的 IDE：Agent 生成组件，保存到可配置存储，再挂载到预览区域；包含编辑器、对象树和 Agent 面板。 | Web；源码运行，使用 Bun 服务端与 NSH Web 界面。 | [源码与项目说明](https://github.com/0x1d/nshde#readme) · [NSH 入口](https://github.com/0x1d/nshde/blob/main/App.tsx) |

## 笔记与文档

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| --- | --- | --- | --- |
| **Mado** | 面向 AI 生成的计划、规格和报告的 Markdown 阅读器；提供文件夹工作区、大纲、搜索、源码／分栏编辑及 HTML、PDF 导出与分享。 | macOS；商业应用，官方展厅未提供源码链接。 | [官网](https://madomd.com/) · [官方收录](https://nsh.dev/apps/mado/) |
| **StoatMD** | 本地 Markdown 笔记本，支持源码、分栏与阅读视图，以及 Google Drive、Dropbox 同步，便于与 Agent 共用文件夹。 | macOS、Windows、Linux、iOS／iPadOS，按当前仓库声明；桌面免费，官方 iOS 版付费。**源码可用，采用 PolyForm Noncommercial 许可。** | [官网](https://stoatmd.com/) · [源码、平台与许可说明](https://github.com/richcalls/stoatmd#readme) · [官方收录](https://nsh.dev/apps/stoatmd/) |
| **Rike（日课）** | 兼容部分 Logseq 文件格式的大纲笔记工具，包含每日页面、双向链接、块引用、任务和搜索；笔记保存在本地 Markdown 中。 | Linux（GTK 4）；**M1 原型，开发中**。Rust 处理数据，NSH TSX 实现界面。 | [源码与实现说明](https://github.com/specter119/rike#readme) · [应用配置](https://github.com/specter119/rike/blob/master/ui/nsh.json) |
| **EPUB Viewer（oh-my-epub-viewer）** | EPUB 2／3 阅读器，以固定 A4 纵向版式分页，窗口缩放时保留分页结果；提供目录与键盘操作。 | Windows 为文档明确提供的打包／安装目标；源码也声明 macOS、Linux 后端。正文通过应用内 WebView 显示。 | [源码与项目说明](https://github.com/demolabskr/oh-my-epub-viewer#readme) · [NSH 依赖](https://github.com/demolabskr/oh-my-epub-viewer/blob/main/Cargo.toml) |

StoatMD 的官方展厅介绍仍列 macOS、iOS 和 TestFlight；本表的平台及源码状态采用核实时更新的项目仓库说明。

## 系统与安全工具

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| -------------------------- | -------------------------------- | --------------------------------- | --------- |
| **sysmon** | 原生系统监视器，展示 CPU、GPU、内存、磁盘、网络和应用活动，并识别开发服务器、编码助手及 Docker 工作负载。 | macOS、Windows、Linux、iOS、Android；公开源码。 | [源码](https://github.com/huacnlee/sysmon) · [官方收录](https://nsh.dev/apps/sysmon/) |
| **Disktree** | 使用嵌套矩形树图展示磁盘空间，支持缩放、目录导航及在确认后将选定文件移至系统废纸篓；当前界面为 Rust 实现。 | macOS、Linux；公开源码，有发布包。 | [官网](https://huacnlee.github.io/disktree/) · [源码](https://github.com/huacnlee/disktree) · [官方收录](https://nsh.dev/apps/disktree/) |
| **我的 Mac 设置和开发工具安装（my-mac-tool）** | 集中管理 macOS 设置、显示器配置、开发工具安装、后台活动与进程规则；使用纯 Rust NSH 界面。 | macOS；已有发布版本。 | [源码与功能说明](https://github.com/gakaki/my-mac-tool#readme) · [NSH 依赖](https://github.com/gakaki/my-mac-tool/blob/main/toolchain-installer/Cargo.toml) |
| **Omawarden App** | Bitwarden／Vaultwarden 客户端，提供密码库浏览、TOTP、密码与口令生成、SSH 密钥和解锁交互；TSX 界面连接 Rust 引擎。 | 主要目标为 Linux（GTK 4）；其他 NSH 平台处于结构适配范围。**早期实验项目，尚不适合生产使用。** | [源码与项目状态](https://github.com/omawarden/omawarden-app#readme) · [应用配置](https://github.com/omawarden/omawarden-app/blob/main/nsh.json) |

## 文件传输与网络

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| --- | --- | --- | --- |
| **Omasend** | 兼容 LocalSend 协议的局域网传输客户端，可发送文件、文件夹、截图、录屏和文本，无需账号或云端上传。 | Linux、macOS、Windows、Android、iOS；公开源码。 | [官网](https://huacnlee.github.io/omasend/) · [源码](https://github.com/huacnlee/omasend) · [官方收录](https://nsh.dev/apps/omasend/) |
| **TFTP Studio** | 原生桌面 TFTP 客户端与服务端，支持上传／下载、协议选项协商、重试、传输进度及活动日志。 | macOS、Windows、Linux；文档提供源码运行和各平台打包脚本。 | [源码与项目说明](https://github.com/ohmycloud/tftp#readme) · [应用配置](https://github.com/ohmycloud/tftp/blob/master/nsh.json) |

## 音乐与游戏

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| --- | --- | --- | --- |
| **Zeedle（NSH 移植版）** | 本地音乐播放器，支持曲库搜索、同步歌词跳转、实时频谱、歌曲元数据和封面编辑；Rust／Rodio 负责音频。 | Windows x64、Linux x64、macOS Apple Silicon；提供便携发布包。 | [NSH 版源码](https://github.com/Jordan-Haidee/zeedle-nsh) · [官方收录](https://nsh.dev/apps/zeedle-nsh/) |
| **弈境（YI JING）** | 棋类应用，包含五子棋、围棋、六子冲、飞行棋、中国跳棋、国际象棋、中国象棋和军棋，提供 AI 对战、教学、残局与棋谱回放。 | Windows、Linux、macOS、Android、Web 有发布包；iOS 支持本地签名打包，未由 CI 发布。 | [源码与平台说明](https://github.com/ywenhao/gomoku#readme) · [应用配置](https://github.com/ywenhao/gomoku/blob/main/nsh.json) |

Zeedle 此处专指 `zeedle-nsh`；其原始 Zeedle 项目使用 Slint，不作为 NSH 应用重复收录。

## 教育

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| --- | --- | --- | --- |
| **BEUConnect** | 面向 BEU 学生的工具，提供课程大纲、历年试题、成绩、排名、出勤、课表与通知，支持离线使用。 | Android；提供 APK。仓库中的配套网站使用 Astro，**NSH 用于 Android 应用**。 | [网站](https://beu.prit.eu.org/) · [源码与原生应用说明](https://github.com/pritkr/beuConnect#readme) · [应用配置](https://github.com/pritkr/beuConnect/blob/main/native/nsh.json) |

## 金融与研究

| 应用 | 简介 | 平台与状态 | 链接与 NSH 依据 |
| --- | --- | --- | --- |
| **Longbridge AI（NSH 桌面版）** | AI 投资研究工作台，TSX 实现界面，Rust 负责认证、Longbridge SDK、流式传输与桌面生命周期。 | Linux 为当前验收平台；macOS、Windows 启动路径尚未验收。源码运行。 | [源码与平台说明](https://github.com/longbridge/nsh-longbridge-ai#readme) · [应用配置](https://github.com/longbridge/nsh-longbridge-ai/blob/main/nsh.json) |

## 演示与原型

以下项目用于学习、验证组件或探索产品，不计入上面的 20 个应用项目。

| 项目 | 内容 | 平台／定位 | 链接与依据 |
| --- | --- | --- | --- |
| **NSH Gallery** | 完整 TSX 示例应用，展示导航、表单、列表、手势、动画、画布和文本等能力。 | 官方示例；Web 可在线体验，同一代码可运行于移动端和桌面。 | [在线体验与说明](https://nsh.dev/gallery/) · [源码](https://github.com/longbridge/nsh/tree/main/examples/gallery) |
| **RichText Demo** | 基于 `nsh-richtext` 和 NSH `RichEditor` 的 Markdown／富文本编辑示例。 | macOS、Windows、Linux、Web；作者明确说明是演示，非持续维护的产品。 | [仓库与定位说明](https://github.com/huacnlee/nsh-richtext#readme) · [示例源码](https://github.com/huacnlee/nsh-richtext/tree/main/examples/demo) |
| **NSH Lab** | 交互式功能实验室，按侧栏分组试用 Tailwind、Shader、SVG、图片和列表等功能。 | 文档提供桌面、Web、iOS、Android 运行方式；部分功能依赖作者的 NSH 分支。 | [源码与运行说明](https://github.com/dXnSix/nsh-lab#readme) |
| **XQ Panel Demo** | 台股自选报价、搜索、明细和行情压力测试的小面板。 | Linux GTK 4 原型已运行；文档另提供 macOS、Windows 启动方式。不是完整 XQ 客户端。 | [源码与范围说明](https://github.com/tina-moneydj/nsh-xq-panel-demo#readme) |

## 官方资源

- [NSH 官网](https://nsh.dev/)：框架介绍与入口。
- [文档](https://nsh.dev/docs/)：Rust／TSX 开发、平台支持和嵌入方式。
- [框架源码](https://github.com/longbridge/nsh)：实现与官方示例。
- [App Stories](https://nsh.dev/apps/)：官方应用展厅；核实时共收录 7 个应用，本清单均已包含。
- [Showcase 仓库](https://github.com/longbridge/nsh-showcases)：应用清单、项目介绍与截图，也是核实应用使用 NSH 的主要来源之一。

## 收录与维护

1. **有使用依据。** 项目说明明确使用 NSH，或源码包含实际 NSH 依赖、入口及应用配置；商业应用可用官方展厅或作者说明作为依据。
2. **按用途归类。** 同一应用只出现一次；移植版标明对应版本，改名项目保留旧名便于查找。
3. **平台具体到应用。** 区分已发布、源码运行、尚未验收和计划支持，不从框架支持范围推断应用可用性。
4. **保留状态与许可边界。** 实验项目、Beta 和演示明确标注；“公开源码”不等同于采用开源许可证，复用代码前请查看各项目许可。
5. **不纳入纯生态设施。** 框架分支、语言绑定、组件库本体、空壳模板，以及仅提及 NSH 的项目不计为应用；有独立演示应用的可列入演示区。

资料优先级：项目当前 README／源码、发布说明与官网，其次为官方 Showcase。条目链接同时作为核实来源；平台与发布状态均为资料核对结果，未逐一下载或运行。后续新增条目请附应用名称、用途、平台、官网或源码链接，以及使用 NSH 的直接依据。