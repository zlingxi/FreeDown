# FreeDown

[English](../../README.md) | [简体中文](./README.zh-CN.md) | [繁體中文](./README.zh-TW.md) | [日本語](./README.ja.md) | **한국어**

![Architecture](https://img.shields.io/badge/Architecture-Desktop%20%C2%B7%20Python%2FQt%20%C2%B7%20yt--dlp%20engine-9B59B6?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.14%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![GUI](https://img.shields.io/badge/GUI-PySide6%20%C2%B7%20Qt%206-41CD52?style=flat-square&logo=qt&logoColor=white)
![Engine](https://img.shields.io/badge/Engine-yt--dlp-1F2937?style=flat-square)
![FFmpeg](https://img.shields.io/badge/FFmpeg-merge%20%C2%B7%20transcode-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![Packaging](https://img.shields.io/badge/Packaging-Nuitka-333333?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows%20%C2%B7%20macOS%20arm64-0078D6?style=flat-square&logo=windows&logoColor=white)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=flat-square)

[yt-dlp](https://github.com/yt-dlp/yt-dlp)와 FFmpeg를 기반으로 제작된 무료 **빌리빌리(bilibili) 전용** 동영상 다운로더.

> 이 프로젝트는 VideosDown(버전 4.0.0)에서 방금 파생되었습니다. 현재는 **무료 설치 패키지를 먼저 배포**하고 있으며, 전체 소스 코드는 추후 [GPL-3.0](../../LICENSE) 라이선스로 공개될 예정입니다.

## ✨ 주요 기능

- **빌리빌리 전용**: BV/AV 단일 영상, 뱅우미(번극), 멀티파트 선택(`?p=N`), 공식 단축 링크 `b23.tv`
- **화질 선택**: 파싱 결과에서 원하는 해상도 선택, 로그인 시 고해상도 선택 가능
- **커버 이미지 다운로드**: 영상과 함께 커버 이미지 저장
- **Cookie 인증**: 대회원/고해상도 로그인 상태 지원(Firefox에서 자동 가져오기 / cookies.txt 수동 가져오기)
- **로컬 영상 트랜스코딩**: FFmpeg 기반 변환, GPU 가속 지원
- **라이트/다크 테마**: 빌리빌리 핑크 테마 색상, 시스템 언어 따르기
- **사이트 가드**: 빌리빌리 도메인만 허용(솔트 해시 화이트리스트 + 파싱/다운로드 전 구간 다중 강제 검증)
## 🖼 스크린샷

| ☀️ 라이트 | 🌙 다크 |
|:---:|:---:|
| ![새 작업 - 라이트](../../assets/home_light.png) | ![새 작업 - 다크](../../assets/home_dark.png) |
| ![파싱 결과 - 라이트](../../assets/result_light.png) | ![파싱 결과 - 다크](../../assets/result_dark.png) |
| ![다운로드 목록 - 라이트](../../assets/tasks_light.png) | ![다운로드 목록 - 다크](../../assets/tasks_dark.png) |

## 🚀 다운로드 및 설치 (무료)

[Releases](https://github.com/zlingxi/FreeDown/releases)에서 설치 패키지를 다운로드하세요:

- **Windows**: `FreeDown-<버전>-Windows-x64.exe`
- **macOS**: `FreeDown-<버전>-MacOS-arm64.dmg`(**Apple Silicon / M 시리즈 칩 전용**)

> 무료 배포 단계에서는 위 두 플랫폼만 제공되며, Intel 칩 Mac은 현재 지원하지 않습니다.

> ⚠️ **참고**: 동영상 플랫폼은 API를 언제든 변경할 수 있어 파싱·다운로드 기능이 작동하지 않게 될 수 있습니다. 문제가 발생하면 [Releases 페이지](https://github.com/zlingxi/FreeDown/releases)를 주시하고 제때 최신 버전으로 업데이트하세요.

## 🧪 소스 코드 공개 (예정)

소스 코드를 정리 중이며, 곧 이 저장소에서 GPL-3.0 라이선스로 공개될 예정입니다. 공개 후 소스에서 실행할 수 있습니다:

```bash
git clone https://github.com/zlingxi/FreeDown.git
cd FreeDown
uv sync
uv run freedown.py
```

실행 환경: Python ≥ 3.14, [uv](https://docs.astral.sh/uv/) 사용을 권장합니다.

## 📦 빌드

```bash
# Windows(Inno Setup 필요) / macOS(create-dmg 필요)
uv run build_app.py
```

## 🗂 디렉터리 구조

```
freedown.py            # 진입점
app/
  parse/               # 사이트 가드 + URL 분류 + 파싱 오케스트레이션
  interface/           # 메인 UI: 새 작업 / 파싱 결과 / 다운로드 / 트랜스코딩
  page/                # 설정, 툴박스 등 대화상자
  common/              # 다운로드 코어, 업데이트, 테마, 로그 등
  thread/              # QThread 워커
  widgets/             # 재사용 위젯
  resources/           # QSS / 아이콘 / ffmpeg
tools/                 # 릴리스 보조 스크립트
```

## ⚠️ 면책조항

본 소프트웨어는 학습 및 연구 목적으로만 사용할 수 있습니다. 다운로드한 콘텐츠의 저작권은 원저작자에게 있으며, 유료/회원 콘텐츠는 본인 계정의 로그인 상태가 필요합니다. 상업적 이용 및 권리 침해 배포는 엄격히 금지됩니다. 전체 내용은 앱 내 '면책조항' 페이지를 참고하세요.

## 📄 라이선스

[GPL-3.0](../../LICENSE) © 2026 FreeDown contributors. VideosDown(4.0.0 이전 버전은 MIT 라이선스)에서 파생되었습니다. 추가 사항:

- 이 프로젝트를 포크하여 지원 사이트 범위를 수정하는 행위는 수정자 본인의 책임이며, 본 프로젝트와는 무관합니다;
- 다운로드한 콘텐츠의 저작권은 원저작자에게 있으며, 본 소프트웨어는 학습·연구 목적으로만 사용해야 합니다;
- 의존하는 서드파티 오픈소스 구성 요소(yt-dlp, FFmpeg, PySide6 등)의 라이선스와 저작권은 각 저작자에게 있습니다.
