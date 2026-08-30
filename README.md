# Focus — Codex Active Island

把 Codex 工作状态、待办、专注倒计时与每日笔记放进桌面顶部的一座“灵动岛”。

> 面向 Windows 与 macOS 的桌面效率工具：看得见 AI 是否正在工作，也能在同一处管理今天要完成的事。

当前开发版本：`0.3.0-alpha.1`（Windows + macOS Apple Silicon）

最新 Windows 稳定版：`0.2.3`

## 核心体验

| 场景 | Focus 能做什么 |
|---|---|
| **Codex 状态可视化** | 像素机器人用睡觉、工作、完成和失败状态，直观展示 Codex 当前进度 |
| **桌面灵动岛** | 常驻屏幕顶部，可展开、收起、隐藏、拖动，并保留当前任务与倒计时 |
| **专注管理** | 管理今日/明日待办，为任务启动倒计时，支持暂停、续时与提前完成 |
| **Obsidian 每日笔记** | 每天保存为 `YYYY-MM-DD.md`；目录设在 Vault 内即可直接进入 Obsidian |
| **轻量提醒** | 提供喝水、久坐提醒，以及完成、失败和提醒声效 |

## 它如何工作

```text
开始任务 → Codex 状态同步到灵动岛 → 专注倒计时
        → 完成 / 失败提示 → 记录到待办与每日笔记
```

Codex 状态依据任务是否正在执行判断，与窗口是否打开无关。收起灵动岛后，仍可查看当前任务、剩余待办和倒计时。

## 更多功能

- 今日与明日待办：新增、编辑、完成、删除、拖动排序。
- 文本和图片剪贴板历史：复制、收藏、删除和清空。
- 系统媒体控制：播放、暂停、上一首和下一首。
- 外观自定义：透明度、尺寸、位置、颜色和音量。
- 系统托盘与开机启动。
- 数据默认保存在本机，不主动上传待办、笔记或剪贴板。

## 下载安装

前往仓库的 **Releases** 页面，下载：

```text
Focus_0.2.3_x64-setup.exe
```

双击即可安装，普通使用不需要 Rust、Node.js 或其他开发环境。

> 安装包目前没有商业代码签名。如果 Windows SmartScreen 提示未知发布者，请先确认文件来自本仓库，再选择“更多信息”继续运行。

macOS Apple Silicon Alpha 可通过 **Build macOS Alpha** GitHub Actions 工作流构建。当前产物未签名，详细说明见 [docs/macos-alpha.md](docs/macos-alpha.md)。

## 从源码运行

二次开发或自行构建需要 Node.js 20+、Rust/Cargo，以及对应平台的构建环境。

```bash
git clone https://github.com/sunkeke-ai/Codex-active-island.git
cd Codex-active-island
npm install
npm run tauri -- dev
```

编译检查：

```bash
npm run build
cd src-tauri
cargo check
```

生成当前平台安装包：

```bash
npm run tauri -- build --bundles nsis
```

## 技术栈

Tauri 2 · React 19 · TypeScript · Vite · Rust · Lucide

## 数据、隐私与已知限制

- 待办、笔记、外观和提醒数据默认保存在本机。
- 剪贴板可能包含敏感内容；“全部清空”也会删除收藏记录。
- Windows 是当前稳定平台；macOS Apple Silicon 仍处于 Alpha。
- 暂无应用内自动更新，需要从 Releases 手动安装新版。
- Codex 本地事件格式变化时，状态联动可能需要重新适配。
- 上传源码前，请勿提交 `.env`、个人待办或本地状态文件。

## 来源与许可

本项目基于 [zzliu93-debug/FocuSD](https://github.com/zzliu93-debug/FocuSD) 定制开发。

公开分发或接受贡献前，请确认原项目的许可要求，并为本仓库补充适用的 `LICENSE` 文件。
