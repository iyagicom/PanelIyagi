# PanelIyagi
GNOME Shell DBus bridge for PanelIyagi panel
# PanelIyagi (패널이야기)

Ubuntu GNOME 환경을 위한 **커스텀 Qt6 패널/작업표시줄**입니다.

GNOME Shell Extension과 D-Bus로 연동하여 창 목록 추적, 앱 실행, 빠른 설정을 하나의 패널에서 제공합니다.

> **Ubuntu 전용** — X11(XCB) 프로토콜 기반. Wayland 세션에서도 XCB 모드로 강제 실행.

---

## ✨ 주요 기능

### 앱 런처
* **카테고리별 앱 표시** — freedesktop 카테고리 (인터넷 · 미디어 · 개발 · 게임 등)
* **즐겨찾기** — 클릭 횟수 기반 자주 쓰는 앱 자동 상단 표시 (최대 20개)
* **실시간 검색** — 앱 이름 · 일반이름 동시 검색
* **프로그램 등록** — 카테고리 우클릭 → .desktop 파일 직접 생성
* **아이콘 자동 탐색** — Yaru 테마 → GNOME 폴백 체인 → /usr/share/pixmaps → 직접 탐색

### 작업표시줄
* **실행 창 목록** — GNOME Shell Extension과 D-Bus로 창 상태 실시간 동기화
* **앱 고정** — 자주 쓰는 앱 왼쪽 영역에 고정 (우클릭 → 고정/해제)
* **활성 창 하이라이트** — 현재 포커스 창 시각적 표시
* **최소화/포커스 토글** — 버튼 클릭으로 창 최소화 ↔ 포커스 전환

### 계산기
* **패널 팝업** — 🧮 버튼 클릭 시 인라인 팝업으로 즉시 계산
* **독립 창** — 팝업에서 새 창 버튼으로 별도 계산기 창 열기
* **히스토리** — 계산 결과 목록, 천 단위 쉼표 자동 포맷
* **항상 위** — 독립 창 우클릭으로 항상 위 고정 가능

### 시스템 트레이
* **XEMBED 표준** — Telegram · Discord · ClipIyagi 등 트레이 아이콘 표시

### 시계 + 달력/메모
* **시계** — 시:분 + 날짜 2줄 표시, 클릭 시 팝업
* **달력** — 날짜별 메모 (기록 있는 날 하이라이트)
* **메모** — 카테고리 + 페이지 계층 구조, SQLite 저장
* **전체 검색** — 달력 메모 + 일반 메모 통합 검색
* **포스트잇** — 바탕화면에 고정되는 메모 창 (세션 재시작 후 복원)

### 빠른 설정
* **볼륨** — 슬라이더 · 음소거 · 마우스 휠 조정
* **Wi-Fi** — 켜기/끄기 · 네트워크 목록 · 비밀번호 입력 후 연결
* **블루투스** — 켜기/끄기 · 페어링 기기 목록 · 연결/해제
* **배터리** — 잔량 % + 상태 (충전 중 / 사용 중 / 완충), 배터리 있을 때만 표시

### IME 입력 모드 표시
* **한/영 실시간 표시** — IBus 입력 모드를 패널에 직접 표시 (한국어 주황색 · 영어 회색)

### 전원 메뉴
* 로그아웃 · 다시 시작 · 시스템 종료

### 우클릭 메뉴
* 아이콘 크기 (24 / 32 / 40 / 48 px) · 아이콘 정렬 (왼쪽 / 가운데)
* 패널 위치 (상단 / 하단) · 패널 환경설정 다이얼로그
* 시스템 설정 바로가기 (Wi-Fi · 블루투스 · 디스플레이 · 소리 · 전원 · 마우스 · 프린터)
* 시스템 감시자

### 확장 인디케이터
* GNOME 화면녹화 / 화면공유 인디케이터 실시간 표시
* Desktop Icons 등 Extension 알림 버튼

### 다국어 지원
* 시스템 언어가 한국어이면 한국어, 그 외에는 영어 UI 자동 선택

---

## 🎮 조작

| 동작 | 방법 |
|---|---|
| 앱 런처 열기 | 앱표시 버튼 (⊞) 클릭 또는 hover |
| 빠른 설정 열기 | 🔊 버튼 클릭 |
| 달력/메모 열기 | 시계 클릭 |
| 계산기 열기 | 🧮 버튼 클릭 |
| 패널 설정 | 패널 우클릭 → 🔧 패널 설정 |
| 앱 고정 | 작업표시줄 버튼 우클릭 → 고정 |
| 볼륨 조정 | 빠른 설정에서 마우스 휠 |

---

## 🚀 설치

### 1. 최신 바이너리 다운로드

[GitHub Releases](https://github.com/iyagicom/PanelIyagi/releases) 에서 최신 버전 다운로드 후 압축 해제.

```
PanelIyagi/
├── PanelIyagi                          ← 실행 파일
└── extension/paneliyagi@iyagi.com/     ← GNOME Shell 확장
```

### 2. GNOME Shell Extension 설치

```bash
bash extension/install.sh

gnome-extensions enable paneliyagi@iyagi.com
```

GNOME Shell 재시작이 필요하면 로그아웃 후 재로그인.

### 3. PanelIyagi 실행

```bash
chmod +x PanelIyagi
./PanelIyagi &
```

### 4. 자동시작 등록 (권장)

패널 우클릭 → **⚙ 설정** → **부팅 시 자동 시작** 체크.

또는 직접 등록:

```bash
mkdir -p ~/.config/autostart
cat > ~/.config/autostart/paneliyagi.desktop << 'EOF'
[Desktop Entry]
Type=Application
Name=PanelIyagi
Exec=/path/to/PanelIyagi
Hidden=false
X-GNOME-Autostart-enabled=true
EOF
```

---

## ⚙ 설정 파일 위치

| 내용 | 경로 |
|---|---|
| 패널 설정 (위치·크기·고정앱) | `~/.config/PanelIyagi/PanelIyagi.conf` |
| 달력/메모 SQLite DB | `~/.local/share/PanelIyagi/paneliyagi.db` |
| 포스트잇 위치/크기 | `~/.config/PanelIyagi/stickynotes.ini` |
| 앱 클릭 횟수 (즐겨찾기) | `~/.config/PanelIyagi/app_clicks.ini` |

---

## 🏗 아키텍처

```
PanelIyagi (Qt6 + XCB)
│
├── Engine         — D-Bus 서비스 (org.iyagi.Engine)
│     └── EngineAdaptor — D-Bus XML 인터페이스
│
├── Panel          — 메인 패널 창 (_NET_WM_WINDOW_TYPE_DOCK)
│     ├── AppLauncherPopup — 앱 런처 팝업
│     ├── TaskButton       — 실행 창 버튼
│     ├── PinnedButton     — 고정 앱 버튼
│     ├── TrayManager      — XEMBED 시스템 트레이
│     ├── IME Label        — 한/영 입력 모드 표시
│     ├── ClockWidget      — 시계 (클릭 가능)
│     ├── CalcPopup        — 계산기 팝업
│     ├── CalcWindow       — 계산기 독립 창
│     ├── ClockPopup       — 시계 팝업 → NoteWindow
│     ├── QuickPanel       — 빠른 설정 팝업
│     └── SettingsDialog   — 패널 환경설정
│
├── NoteWindow     — 달력/메모/검색 창
│     ├── MemoDB   — SQLite 저장소
│     └── StickyNote — 바탕화면 포스트잇
│
└── GNOME Shell Extension (paneliyagi@iyagi.com)
      └── D-Bus → Engine — 창 이벤트·앱 실행 중개
```

---

## 🖥 지원 플랫폼

* Ubuntu 22.04 / 24.04 (GNOME 46, X11 또는 Wayland+XCB)
* Qt 6.2+

---

## 👤 개발자

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 라이선스

Copyright (c) 2026 IYAGI INC. All rights reserved.

이 소프트웨어는 **실행 파일 형태로만 제공됩니다.** 소스 코드는 공개되지 않습니다.

개인적 및 비상업적 용도로 사용할 수 있습니다.
작성자의 명시적 서면 허가 없이 재배포, 수정, 리버스 엔지니어링을 금지합니다.
