# Awesome NSH

English | [Chinese](README-zh.md)

A collection of applications built with [Native Shell (NSH)](https://nsh.dev/), organized by use case, with platforms, project status, and sources.

NSH is a native UI framework developed by Longbridge. Applications can be written in Rust, TSX, or both, and NSH can also be embedded in existing applications. Each application's platform support is listed according to its own documentation, rather than inferred from the framework's supported platforms.

**Last verified: 2026-11-05.** This list includes **20 application projects**, including projects in development, plus **4 demos and prototypes**. It is based on public documentation and does not claim to cover every NSH application. The applications have not been installation-tested for this list.

## Contents

- [AI and Developer Tools](#ai-and-developer-tools)
- [Notes and Documents](#notes-and-documents)
- [System and Security Tools](#system-and-security-tools)
- [File Transfer and Networking](#file-transfer-and-networking)
- [Music and Games](#music-and-games)
- [Education](#education)
- [Finance and Research](#finance-and-research)
- [Demos and Prototypes](#demos-and-prototypes)
- [Official Resources](#official-resources)
- [Inclusion and Maintenance](#inclusion-and-maintenance)

## AI and Developer Tools

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **Noop** | Runs teams of Claude Code and Codex agents on your own computers to handle tasks, scheduled work, and decisions requiring human input. Machine and task status can be viewed across devices. | macOS, Windows, Linux, iOS, Android, Web; public source code. | [Website](https://huacnlee.github.io/noop/) · [Source](https://github.com/huacnlee/noop) · [Official listing](https://nsh.dev/apps/noop/) |
| **Somtus (formerly RiWork)** | A native workspace with Ghostty terminals, persistent tmux sessions, projects, Git worktrees, and agent management across machines. | macOS; **Beta**. The iOS client is being migrated to NSH while retaining some existing native interfaces. | [Source and project documentation](https://github.com/Rhein-Industries/riWork#readme) · [NSH application configuration](https://github.com/Rhein-Industries/riWork/blob/main/apps/riwork/nsh.json) |
| **callme** | An API client that stores requests in plain-text `.http` files. The desktop application, CLI, and MCP server share request execution, with response browsing, environment variables, and streaming responses. | The desktop documentation currently provides macOS build instructions; runs from source. NSH powers the desktop UI; the CLI and core library are independent of NSH. | [Source and NSH implementation details](https://github.com/lvwxx/callme#built-with-nsh) · [Application configuration](https://github.com/lvwxx/callme/blob/main/app/nsh.json) |
| **Toolbook** | Turns tools for JSON, JWT, regular expressions, HTTP, and more into Markdown code blocks. Blocks pass data through `$name` references and recompute automatically. The same note can also be run through the CLI or by an agent. | macOS; release packages available. The v1 interface is in Chinese. | [Website](https://wenlingang.github.io/toolbook/) · [Source and project documentation](https://github.com/wenlingang/toolbook#readme) |
| **Grok Shell** | Lets a model generate TSX modules during a conversation, then compiles and hot-updates them into native interactive interfaces. Generated components can be saved as Mini Apps. | macOS (AppKit); runs from source using an NSH fork. | [Source and technical stack](https://github.com/hexuria/grok-shell#tech-stack) |
| **nshde** | An IDE that can extend itself at runtime: agents generate components, save them to configurable storage, and mount them in a preview area. Includes an editor, object tree, and agent panel. | Web; runs from source with a Bun server and an NSH Web interface. | [Source and project documentation](https://github.com/0x1d/nshde#readme) · [NSH entry point](https://github.com/0x1d/nshde/blob/main/App.tsx) |

## Notes and Documents

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **Mado** | A Markdown reader for AI-generated plans, specifications, and reports, with folder workspaces, outlines, search, source and split editing, HTML/PDF export, and sharing. | macOS; commercial application. The official showcase does not provide a source link. | [Website](https://madomd.com/) · [Official listing](https://nsh.dev/apps/mado/) |
| **StoatMD** | A local Markdown notebook with source, split, and reading views, plus Google Drive and Dropbox sync, allowing users and agents to share the same folders. | macOS, Windows, Linux, iOS/iPadOS, as stated in the current repository. Desktop is free; the official iOS application is paid. **Source-available under the PolyForm Noncommercial license.** | [Website](https://stoatmd.com/) · [Source, platforms, and licensing](https://github.com/richcalls/stoatmd#readme) · [Official listing](https://nsh.dev/apps/stoatmd/) |
| **Rike** | An outliner supporting a subset of the Logseq file format, with daily pages, bidirectional links, block references, tasks, and search. Notes are stored as local Markdown files. | Linux (GTK 4); **M1 prototype, in development**. Rust handles data, and NSH TSX implements the interface. | [Source and implementation details](https://github.com/specter119/rike#readme) · [Application configuration](https://github.com/specter119/rike/blob/master/ui/nsh.json) |
| **EPUB Viewer (oh-my-epub-viewer)** | An EPUB 2/3 reader with fixed A4 portrait pagination that remains stable when the window is resized, plus a table of contents and keyboard controls. | Windows is the explicitly documented packaging and installation target; the source also declares macOS and Linux backends. Book content is displayed in an embedded WebView. | [Source and project documentation](https://github.com/demolabskr/oh-my-epub-viewer#readme) · [NSH dependencies](https://github.com/demolabskr/oh-my-epub-viewer/blob/main/Cargo.toml) |

StoatMD's official showcase entry still lists macOS, iOS, and TestFlight. The platforms and source availability above follow the newer repository documentation available at verification time.

## System and Security Tools

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **sysmon** | A native system monitor showing CPU, GPU, memory, disk, network, and application activity, with detection of development servers, coding assistants, and Docker workloads. | macOS, Windows, Linux, iOS, Android; public source code. | [Source](https://github.com/huacnlee/sysmon) · [Official listing](https://nsh.dev/apps/sysmon/) |
| **Disktree** | Visualizes disk usage as a nested treemap, with zooming, directory navigation, and confirmed removal of selected files to the system Trash. The current interface is implemented in Rust. | macOS, Linux; public source code and release packages. | [Website](https://huacnlee.github.io/disktree/) · [Source](https://github.com/huacnlee/disktree) · [Official listing](https://nsh.dev/apps/disktree/) |
| **My Mac Settings and Developer Tool Installer (my-mac-tool)** | Manages macOS settings, display configuration, developer tool installation, background activity, and process rules through a pure Rust NSH interface. | macOS; a published release is available. | [Source and features](https://github.com/gakaki/my-mac-tool#readme) · [NSH dependencies](https://github.com/gakaki/my-mac-tool/blob/main/toolchain-installer/Cargo.toml) |
| **Omawarden App** | A Bitwarden/Vaultwarden client with vault browsing, TOTP, password and passphrase generation, SSH keys, and unlock interactions. Its TSX interface connects to a Rust engine. | Primarily targets Linux (GTK 4); structured for adaptation to other NSH platforms. **An early experimental project, not ready for production use.** | [Source and project status](https://github.com/omawarden/omawarden-app#readme) · [Application configuration](https://github.com/omawarden/omawarden-app/blob/main/nsh.json) |

## File Transfer and Networking

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **Omasend** | A LocalSend-compatible LAN transfer client for files, folders, screenshots, recordings, and text, with no account or cloud upload required. | Linux, macOS, Windows, Android, iOS; public source code. | [Website](https://huacnlee.github.io/omasend/) · [Source](https://github.com/huacnlee/omasend) · [Official listing](https://nsh.dev/apps/omasend/) |
| **TFTP Studio** | A native desktop TFTP client and server supporting uploads, downloads, protocol option negotiation, retries, transfer progress, and activity logs. | macOS, Windows, Linux; documentation provides instructions for running from source and packaging scripts for each platform. | [Source and project documentation](https://github.com/ohmycloud/tftp#readme) · [Application configuration](https://github.com/ohmycloud/tftp/blob/master/nsh.json) |

## Music and Games

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **Zeedle (NSH port)** | A local music player with library search, synchronized lyric seeking, a live spectrum, and editing of song metadata and artwork. Rust and Rodio handle audio. | Windows x64, Linux x64, macOS Apple Silicon; portable release packages available. | [NSH port source](https://github.com/Jordan-Haidee/zeedle-nsh) · [Official listing](https://nsh.dev/apps/zeedle-nsh/) |
| **YI JING** | A board game application featuring Gomoku, Go, Liu Zi Chong, Aeroplane Chess, Chinese Checkers, Chess, Xiangqi, and Junqi, with AI opponents, tutorials, endgame puzzles, and game replays. | Release packages for Windows, Linux, macOS, Android, and Web. iOS supports locally signed builds and is not published through CI. | [Source and platform documentation](https://github.com/ywenhao/gomoku#readme) · [Application configuration](https://github.com/ywenhao/gomoku/blob/main/nsh.json) |

The Zeedle entry refers specifically to `zeedle-nsh`. The original Zeedle project uses Slint and is not counted separately as an NSH application.

## Education

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **BEUConnect** | Tools for BEU students, including syllabi, past exam papers, results, rankings, attendance, timetables, and notices, with offline support. | Android; APK available. The companion website in the repository uses Astro; **NSH powers the Android application**. | [Website](https://beu.prit.eu.org/) · [Source and native application documentation](https://github.com/pritkr/beuConnect#readme) · [Application configuration](https://github.com/pritkr/beuConnect/blob/main/native/nsh.json) |

## Finance and Research

| Application | Description | Platforms and status | Links and evidence of NSH use |
| --- | --- | --- | --- |
| **Longbridge AI (NSH desktop version)** | An AI investment research workspace with a TSX interface and Rust handling authentication, the Longbridge SDK, streaming, and the desktop lifecycle. | Linux is the currently validated platform. The macOS and Windows launch paths have not been validated. Runs from source. | [Source and platform documentation](https://github.com/longbridge/nsh-longbridge-ai#readme) · [Application configuration](https://github.com/longbridge/nsh-longbridge-ai/blob/main/nsh.json) |

## Demos and Prototypes

These projects are intended for learning, component validation, or product exploration. They are not included in the 20 application projects above.

| Project | Description | Platforms and purpose | Links and evidence |
| --- | --- | --- | --- |
| **NSH Gallery** | A complete TSX example application demonstrating navigation, forms, lists, gestures, animations, canvas, and text. | Official example; available to try on the Web, with the same code running on mobile and desktop. | [Live demo and documentation](https://nsh.dev/gallery/) · [Source](https://github.com/longbridge/nsh/tree/main/examples/gallery) |
| **RichText Demo** | A Markdown and rich text editing example built with `nsh-richtext` and NSH's `RichEditor`. | macOS, Windows, Linux, Web. The author explicitly describes it as a demo rather than an actively maintained product. | [Repository and project scope](https://github.com/huacnlee/nsh-richtext#readme) · [Example source](https://github.com/huacnlee/nsh-richtext/tree/main/examples/demo) |
| **NSH Lab** | An interactive feature lab with sidebar groups for trying Tailwind, shaders, SVG, images, and lists. | Documentation provides desktop, Web, iOS, and Android run instructions. Some features depend on the author's NSH fork. | [Source and run instructions](https://github.com/dXnSix/nsh-lab#readme) |
| **XQ Panel Demo** | A small panel for Taiwan stock watchlist quotes, search, details, and market data stress testing. | A working Linux GTK 4 prototype; documentation also provides macOS and Windows launch instructions. It is not a complete XQ client. | [Source and project scope](https://github.com/tina-moneydj/nsh-xq-panel-demo#readme) |

## Official Resources

- [NSH website](https://nsh.dev/): framework introduction and starting points.
- [Documentation](https://nsh.dev/docs/): Rust/TSX development, platform support, and embedding.
- [Framework source](https://github.com/longbridge/nsh): implementation and official examples.
- [App Stories](https://nsh.dev/apps/): the official application showcase, with 7 applications at verification time, all included here.
- [Showcase repository](https://github.com/longbridge/nsh-showcases): application manifests, descriptions, and screenshots; a primary source for verifying NSH usage.

## Inclusion and Maintenance

1. **Require evidence of NSH use.** Project documentation must explicitly state that it uses NSH, or source code must contain actual NSH dependencies, entry points, and application configuration. Commercial applications may be verified through the official showcase or author documentation.
2. **Organize by use case.** List each application once. Identify ports explicitly and retain former project names to make renamed applications easier to find.
3. **Report application-specific platforms.** Distinguish published builds, source-only usage, unvalidated platforms, and planned support. Do not infer availability from the framework's platform support.
4. **Preserve status and license distinctions.** Label experimental projects, betas, and demos. Public source code does not necessarily mean an open-source license; check each project's license before reusing code.
5. **Exclude infrastructure-only projects.** Framework forks, language bindings, component libraries themselves, empty templates, and projects that merely mention NSH do not count as applications. Their standalone demo applications may be included in the demo section.

Sources are prioritized in this order: current project README and source code, release notes and project websites, then the official showcase. Entry links also provide the verification sources. Platforms and release status were checked against documentation; applications were not individually downloaded or run. To add an entry, provide the application name, purpose, platforms, website or source link, and direct evidence of NSH use.
