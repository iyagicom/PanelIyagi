# 패널이야기 (PanelIyagi)

**우분투 GNOME 에 진짜 작업표시줄을 — 시작 메뉴·작업표시줄·트레이·시계·달력을 한 줄에, 익숙한 그 모습으로.**

[English](README.md) · [한국어](README_ko.md)

![PanelIyagi](paneliyagi.jpg)

## 왜 패널이야기인가

- **익숙한 방식의 GNOME.** 시작 메뉴, 열린 창이 모두 보이는 작업표시줄, 시스템 트레이, 시계가 한 패널에 있습니다. 창을 바꾸려고 "현재 활동" 화면을 열 필요가 없습니다.
- **무엇이든 클릭 한 번.** 분류별 앱, 즐겨찾기, 실시간 검색. 매일 쓰는 앱은 고정해 둡니다.
- **시계 그 이상.** 시계를 누르면 메모가 달린 달력, 포스트잇, 알람, 이달 할일이 나옵니다.
- **패널 속 계산기.** 수식을 통째로 입력하고, 기록을 남기고, 주석을 달고, 골라서 합계를 냅니다.
- **PC 상태가 한눈에.** CPU·메모리 사용량이 패널에 보이고, 음량과 빠른 설정도 클릭 한 번입니다.

## 기능

### 시작 메뉴·작업표시줄
- 분류별 앱 메뉴, 즐겨찾기, 실시간 검색, 프로그램 직접 등록
- 열린 창 목록, 활성 창 표시, 클릭으로 최소화/앞으로
- 앱 고정, 창 묶기, 멈춘 프로그램 강제 종료

### 트레이·상태
- 시스템 트레이(XEMBED), CPU/메모리 표시
- 음량, 빠른 설정

### 시계·달력·메모
- 날짜별 메모와 시간 알람이 있는 달력
- 포스트잇, 이달 할일, 잠깐 메모, 전체 검색

### 계산기
- 패널 팝업 또는 별도 창의 수식 계산기
- 기록, 주석, 선택 합계, 항상 위

## 다운로드

**[⬇ 최신 버전 받기](https://github.com/iyagicom/PanelIyagi/releases/latest)**

| 내 시스템 | 받을 파일 |
|---|---|
| Ubuntu 24.04 · 데비안 | **ubuntu24.04** 가 붙은 `.deb` |
| Ubuntu 26.04 | **ubuntu26.04** 가 붙은 `.deb` |
| 페도라 · openSUSE | `.rpm` |
| 아치 · 만자로 | `.pkg.tar.zst` |
| 그 밖의 리눅스 | `.AppImage` 또는 `.zip` |
| GNOME Shell 확장만 | `paneliyagi-extension-*.zip` |

```bash
sudo apt install ./paneliyagi_*_amd64.deb    # 우분투 / 데비안
sudo dnf install ./paneliyagi-*.rpm          # 페도라
sudo pacman -U paneliyagi-*.pkg.tar.zst      # 아치
```

패키지가 앱과 GNOME Shell 확장을 함께 설치하고 켭니다. GNOME 이 확장을 읽도록 한 번 로그아웃했다가 다시 로그인하세요.

GNOME 용입니다. KDE Plasma·XFCE·Cinnamon·MATE·LXQt·sway 를 쓴다면 **[TaskIyagi](https://github.com/iyagicom/TaskIyagi)** 를 보세요.

## 라이선스

[라이선스](LICENSE)
