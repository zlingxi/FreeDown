# FreeDown

[English](../../README.md) | **简体中文** | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | [한국어](./README.ko.md)

![Architecture](https://img.shields.io/badge/Architecture-Desktop%20%C2%B7%20Python%2FQt%20%C2%B7%20yt--dlp%20engine-9B59B6?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.14%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![GUI](https://img.shields.io/badge/GUI-PySide6%20%C2%B7%20Qt%206-41CD52?style=flat-square&logo=qt&logoColor=white)
![Engine](https://img.shields.io/badge/Engine-yt--dlp-1F2937?style=flat-square)
![FFmpeg](https://img.shields.io/badge/FFmpeg-merge%20%C2%B7%20transcode-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Packaging](https://img.shields.io/badge/Packaging-Nuitka-333333?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows%20%C2%B7%20macOS%20arm64-0078D6?style=flat-square&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=flat-square)

免费的 **bilibili 专用**视频下载工具，基于 [yt-dlp](https://github.com/yt-dlp/yt-dlp) 与 FFmpeg 构建。

> 项目刚从 VideosDown（其 4.0.0 版本）衍生而来：当前**先行免费发布安装包**，
> 完整源码将以 [GPL-3.0](../../LICENSE) 协议随后开源，敬请关注。

## ✨ 功能特性

- **仅支持 bilibili**：BV/AV 单视频、番剧、多P选P（`?p=N`）、`b23.tv` 官方短链
- **画质选择**：按解析结果自选清晰度，登录后可选高清晰度
- **封面下载**：下载视频的同时保存封面图
- **Cookie 授权**：支持大会员/高清晰度登录态（Firefox 自动获取 / 手动导入 cookies.txt）
- **本地视频转码**：FFmpeg 转码，支持 GPU 加速
- **明暗双主题**：B站粉主题色，跟随系统语言
- **站点守卫**：仅放行 bilibili 域名（加盐哈希白名单 + 解析/下载全链路多点强制校验）
## 🖼 界面预览

| ☀️ 浅色主题 | 🌙 深色主题 |
|:---:|:---:|
| ![新建任务 - 浅色](../../assets/home_light.png) | ![新建任务 - 深色](../../assets/home_dark.png) |
| ![解析结果 - 浅色](../../assets/result_light.png) | ![解析结果 - 深色](../../assets/result_dark.png) |
| ![下载任务 - 浅色](../../assets/tasks_light.png) | ![下载任务 - 深色](../../assets/tasks_dark.png) |

## 🚀 下载安装（免费）

前往 [Releases](https://github.com/zlingxi/FreeDown/releases) 下载对应安装包：

- **Windows**：`FreeDown-<版本>-Windows-x64.exe`
- **macOS**：`FreeDown-<版本>-MacOS-arm64.dmg`（仅 **Apple Silicon / M 系列芯片**）

> 免费发布阶段仅提供以上两个平台，Intel 芯片 Mac 暂不提供安装包。

> ⚠️ **提示**：视频平台可能随时调整接口，解析或下载功能存在失效的可能。遇到无法使用时，请关注 [Releases 发布页](https://github.com/zlingxi/FreeDown/releases)，及时更新到最新版本。

## 🧪 源码开源（即将）

源码正在整理中，将很快在本仓库以 GPL-3.0 协议发布。开源后可从源码运行：

```bash
git clone https://github.com/zlingxi/FreeDown.git
cd FreeDown
uv sync
uv run freedown.py
```

运行环境：Python ≥ 3.14，推荐使用 [uv](https://docs.astral.sh/uv/)。

## 📦 构建打包

```bash
# Windows（需要 Inno Setup）/macOS（需要 create-dmg）
uv run build_app.py
```

## 🗂 目录结构

```
freedown.py            # 入口
app/
  parse/               # 站点守卫 + 链接分类 + 解析编排
  interface/           # 主界面：新建/解析/下载/转码
  page/                # 设置、功能面板等对话框
  common/              # 下载核心、更新、主题、日志等
  thread/              # QThread 工作线程
  widgets/             # 复用组件
  resources/           # QSS / 图标 / ffmpeg
tools/                 # 发布辅助脚本
```

## ⚠️ 免责声明

本软件仅供学习与研究使用。下载内容的版权归原作者所有；会员/付费内容需使用你本人账号的
登录态访问。严禁将下载内容用于商业盈利或侵权分发。完整声明见软件内置「免责声明」页。

## 📄 开源协议

以 [GPL-3.0](../../LICENSE) 协议开源 © 2026 FreeDown contributors，衍生自 VideosDown（其 4.0.0
之前的历史版本曾以 MIT 协议发布）。补充说明：

- 任何人 fork 本项目后修改站点支持范围的，属于下游行为，由此产生的一切责任由修改者
  自行承担，与本项目无关；
- 下载内容的版权归原版权方所有，本软件仅供学习与研究使用；
- 依赖的第三方开源组件（yt-dlp、FFmpeg、PySide6 等）的许可与版权归其原作者所有。
