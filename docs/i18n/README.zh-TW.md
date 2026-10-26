# FreeDown

[English](../../README.md) | [简体中文](./README.zh-CN.md) | **繁體中文** | [日本語](./README.ja.md) | [한국어](./README.ko.md)

![Architecture](https://img.shields.io/badge/Architecture-Desktop%20%C2%B7%20Python%2FQt%20%C2%B7%20yt--dlp%20engine-9B59B6?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.14%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![GUI](https://img.shields.io/badge/GUI-PySide6%20%C2%B7%20Qt%206-41CD52?style=flat-square&logo=qt&logoColor=white)
![Engine](https://img.shields.io/badge/Engine-yt--dlp-1F2937?style=flat-square)
![FFmpeg](https://img.shields.io/badge/FFmpeg-merge%20%C2%B7%20transcode-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Packaging](https://img.shields.io/badge/Packaging-Nuitka-333333?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows%20%C2%B7%20macOS%20arm64-0078D6?style=flat-square&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=flat-square)

免費的 **bilibili 專用**影片下載工具，基於 [yt-dlp](https://github.com/yt-dlp/yt-dlp) 與 FFmpeg 構建。

> 本專案剛從 VideosDown（其 4.0.0 版本）衍生而來：目前**先行免費發布安裝包**，
> 完整原始碼將以 [GPL-3.0](../../LICENSE) 授權條款隨後開源，敬請關注。

## ✨ 功能特性

- **僅支援 bilibili**：BV/AV 單影片、番劇、多P選P（`?p=N`）、`b23.tv` 官方短連結
- **畫質選擇**：依解析結果自選清晰度，登入後可選高解析度
- **封面下載**：下載影片的同時儲存封面圖
- **Cookie 授權**：支援大會員/高解析度登入狀態（Firefox 自動取得 / 手動匯入 cookies.txt）
- **本機影片轉碼**：FFmpeg 轉碼，支援 GPU 加速
- **明暗雙主題**：B站粉主題色，跟隨系統語言
- **站點守衛**：僅放行 bilibili 網域（加鹽雜湊白名單 + 解析/下載全鏈路多點強制校驗）
## 🖼 介面預覽

| ☀️ 淺色主題 | 🌙 深色主題 |
|:---:|:---:|
| ![新建任務 - 淺色](../../assets/home_light.png) | ![新建任務 - 深色](../../assets/home_dark.png) |
| ![解析結果 - 淺色](../../assets/result_light.png) | ![解析結果 - 深色](../../assets/result_dark.png) |
| ![下載任務 - 淺色](../../assets/tasks_light.png) | ![下載任務 - 深色](../../assets/tasks_dark.png) |

## 🚀 下載安裝（免費）

前往 [Releases](https://github.com/zlingxi/FreeDown/releases) 下載對應安裝包：

- **Windows**：`FreeDown-<版本>-Windows-x64.exe`
- **macOS**：`FreeDown-<版本>-MacOS-arm64.dmg`（僅 **Apple Silicon / M 系列晶片**）

> 免費發布階段僅提供以上兩個平台，Intel 晶片 Mac 暫不提供安裝包。

> ⚠️ **提示**：影音平台可能隨時調整介面，解析或下載功能存在失效的可能。遇到無法使用時，請關注 [Releases 發布頁](https://github.com/zlingxi/FreeDown/releases)，及時更新到最新版本。

## 🧪 原始碼開源（即將）

原始碼正在整理中，將很快在本倉庫以 GPL-3.0 授權條款發布。開源後可從原始碼執行：

```bash
git clone https://github.com/zlingxi/FreeDown.git
cd FreeDown
uv sync
uv run freedown.py
```

執行環境：Python ≥ 3.14，推薦使用 [uv](https://docs.astral.sh/uv/)。

## 📦 構建打包

```bash
# Windows（需要 Inno Setup）/macOS（需要 create-dmg）
uv run build_app.py
```

## 🗂 目錄結構

```
freedown.py            # 入口
app/
  parse/               # 站點守衛 + 連結分類 + 解析編排
  interface/           # 主介面：新建/解析/下載/轉碼
  page/                # 設定、功能面板等對話框
  common/              # 下載核心、更新、主題、日誌等
  thread/              # QThread 工作執行緒
  widgets/             # 複用元件
  resources/           # QSS / 圖示 / ffmpeg
tools/                 # 發布輔助腳本
```

## ⚠️ 免責聲明

本軟體僅供學習與研究使用。下載內容的版權歸原作者所有；會員/付費內容需使用你本人帳號的
登入狀態存取。嚴禁將下載內容用於商業盈利或侵權散布。完整聲明見軟體內建「免責聲明」頁。

## 📄 開源協議

以 [GPL-3.0](../../LICENSE) 授權條款開源 © 2026 FreeDown contributors，衍生自 VideosDown（其 4.0.0
之前的歷史版本曾以 MIT 授權條款發布）。補充說明：

- 任何人 fork 本專案後修改站點支援範圍的，屬於下游行為，由此產生的一切責任由修改者
  自行承擔，與本專案無關；
- 下載內容的版權歸原版權方所有，本軟體僅供學習與研究使用；
- 依賴的第三方開源元件（yt-dlp、FFmpeg、PySide6 等）的授權與版權歸其原作者所有。
