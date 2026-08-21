# INDEX

이 저장소는 카테고리별 정적 HTML 페이지 아카이브다. "앱별/템플릿별" 구분 축이나 `tmpl_flat`/`tmpl_round` 설계는 이 저장소 어디에도 존재하지 않는다 — 전체 파일을 확인·검색했으나 해당 네이밍·구조는 발견되지 않았다. 아래는 실제 발견된 구조 기준의 색인이다.

---

## 1. 카테고리별

| 카테고리 | 페이지 | 경로 |
|---|---|---|
| bible/History | 이스라엘 분열왕국 연대표 | `pages/bible/History/israel-kings-timeline.html` |
| bible/History | 사도 바울의 전도여행 대화형 대시보드 | `pages/bible/History/Paul_Missionary_Journeys_Map.html` |
| life | AI 날씨 예측 대시보드 | `pages/life/weather_dashboard.html` |

- 루트 `index.html`은 GitHub API로 `pages/` 하위 폴더·파일을 동적으로 읽어 목록을 렌더링하는 홈이다. 정적 앱/템플릿 목록이 아니라 실행 시점에 저장소 구조를 그대로 반영한다.
- `pages/_navbar-preview.html`은 언더스코어 접두 파일로 배포·색인 대상에서 제외된다 (navbar 디자인 미리보기용 작업 파일).

## 2. 페이지별 핵심 특징

| 파일 | 배경/디자인 계열 | 비고 |
|---|---|---|
| `pages/bible/History/israel-kings-timeline.html` | Absolute Black `#000000` + Lamborghini Gold `#FFC000` | 고정 높이 flex 레이아웃, `.sarea` 내부 스크롤 |
| `pages/bible/History/Paul_Missionary_Journeys_Map.html` | 동일 팔레트, Tailwind + Leaflet 지도 | `gold`/`charcoal`/`iron`/`ash` 커스텀 토큰 사용 |
| `pages/life/weather_dashboard.html` | 동일 팔레트, Chart.js | 강수 배경색 3단계(`#0a1c33`/`#0b2847`/`#0d3464`) |

세 페이지 모두 동일한 단일 navbar 디자인(Absolute Black + Gold, 높이 44px/모바일 40px)을 공유한다 — `CLAUDE.md`에 정의된 공통 navbar 규칙. 페이지별 개별 템플릿 번호(001/002/003 등)나 `tmpl_flat`/`tmpl_round` 계열 분기는 코드상 존재하지 않는다.

---

이 색인은 실제 파일 구조 기준 스냅샷이며, `CLAUDE.md`(작업 지침)·`HANDOFF.md`(현황/다음 작업) 내용과 중복 서술하지 않는다.
