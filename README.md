# FreeDown

**English** | [简体中文](docs/i18n/README.zh-CN.md) | [繁體中文](docs/i18n/README.zh-TW.md) | [日本語](docs/i18n/README.ja.md) | [한국어](docs/i18n/README.ko.md)

![Architecture](https://img.shields.io/badge/Architecture-Desktop%20%C2%B7%20Python%2FQt%20%C2%B7%20yt--dlp%20engine-9B59B6?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.14%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![GUI](https://img.shields.io/badge/GUI-PySide6%20%C2%B7%20Qt%206-41CD52?style=flat-square&logo=qt&logoColor=white)
![Engine](https://img.shields.io/badge/Engine-yt--dlp-1F2937?style=flat-square)
![FFmpeg](https://img.shields.io/badge/FFmpeg-merge%20%C2%B7%20transcode-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Packaging](https://img.shields.io/badge/Packaging-Nuitka-333333?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows%20%C2%B7%20macOS%20arm64-0078D6?style=flat-square&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=flat-square)

A free **bilibili-only** video downloader built on [yt-dlp](https://github.com/yt-dlp/yt-dlp) and FFmpeg.

> This project has just been derived from VideosDown (version 4.0.0): **free installers are released first**, and the full source code will be published in this repository soon under [GPL-3.0](LICENSE).

## ✨ Features

- **bilibili only**: BV/AV single videos, bangumi, multi-part selection (`?p=N`), and official `b23.tv` short links
- **Quality selection**: pick the resolution you want from the parse result; higher resolutions available with login state
- **Cover download**: save the video cover image together with the video
- **Cookie authorization**: supports Big Member / high-resolution login state (auto-fetch from Firefox / manual cookies.txt import)
- **Local video transcoding**: FFmpeg transcoding with GPU acceleration
- **Light & dark themes**: bilibili-pink theme color, UI language follows the system
- **Site guard**: only bilibili domains are allowed (salted hash whitelist + multi-point enforcement across the parse/download pipeline)
## 🖼 Screenshots

| ☀️ Light | 🌙 Dark |
|:---:|:---:|
| ![new task - light](assets/home_light.png) | ![new task - dark](assets/home_dark.png) |
| ![parse result - light](assets/result_light.png) | ![parse result - dark](assets/result_dark.png) |
| ![download list - light](assets/tasks_light.png) | ![download list - dark](assets/tasks_dark.png) |

## 🚀 Download & Install (Free)

Get the installer from [Releases](https://github.com/zlingxi/FreeDown/releases):

- **Windows**: `FreeDown-<version>-Windows-x64.exe`
- **macOS**: `FreeDown-<version>-MacOS-arm64.dmg` (**Apple Silicon / M-series chips only**)

> During the free release phase only these two platforms are provided; Intel-chip Macs are not supported for now.

> ⚠️ **Note**: Video platforms may change their APIs at any time, so parsing or downloading may stop working. If that happens, watch the [Releases](https://github.com/zlingxi/FreeDown/releases) page and update to the latest version in time.

## 🧪 Source Code (Coming Soon)

The source code is being prepared and will be published in this repository soon under GPL-3.0. Once available, you can run from source:

```bash
git clone https://github.com/zlingxi/FreeDown.git
cd FreeDown
uv sync
uv run freedown.py
```

Requires Python ≥ 3.14; [uv](https://docs.astral.sh/uv/) is recommended.

## 📦 Build

```bash
# Windows (requires Inno Setup) / macOS (requires create-dmg)
uv run build_app.py
```

## 🗂 Project Layout

```
freedown.py            # entry
app/
  parse/               # site guard + URL classification + parse orchestration
  interface/           # main UI: new task / parse result / downloads / transcode
  page/                # settings, toolbox and other dialogs
  common/              # download core, update, theme, logging, etc.
  thread/              # QThread workers
  widgets/             # reusable widgets
  resources/           # QSS / icons / ffmpeg
tools/                 # release helper scripts
```

## ⚠️ Disclaimer

This software is for learning and research only. Downloaded content is copyrighted by its original owners; paid/member content requires the login state of your own account. Commercial use or infringing distribution is strictly prohibited. See the in-app Disclaimer page for the full text.

## 📄 License

Released under [GPL-3.0](LICENSE) © 2026 FreeDown contributors, derived from VideosDown (whose pre-4.0.0 versions were MIT-licensed). Additional notes:

- Anyone who forks this project and modifies the supported site scope does so at their own risk; this project is not responsible for such derivatives;
- Downloaded content is copyrighted by its original owners; this software is for learning and research only;
- Third-party open-source components (yt-dlp, FFmpeg, PySide6, etc.) remain under their respective authors' licenses.
