# HTML VAULT — 현황 및 인수인계

> 마지막 업데이트: 2026-06-12

---

## 현재 파일 구조

```
web-html-vault/
├── index.html                          # 홈 (DESIGN_Lamborghini.md 기준 리뉴얼 완료)
├── CLAUDE.md                           # 작업 지침
├── LOG.md                              # 작업 로그
├── HANDOFF.md                          # 이 파일
├── README.md
└── pages/
    ├── _navbar-preview.html            # navbar 디자인 미리보기 (배포 제외)
    ├── bible/
    │   └── summary/                    # 향후 maps/, prophecy/ 등 추가 예정
    │       └── israel-kings-timeline.html
    └── life/
        └── weather_dashboard.html
```

---

## 완료된 작업 (2026-06-12 전체 세션)

- [x] 공통 navbar 디자인 확정 및 `CLAUDE.md` 지침 등록
- [x] `_navbar-preview.html` Lamborghini 디자인 미리보기 파일 생성
- [x] `index.html` — DESIGN_Lamborghini.md 기준 전면 리뉴얼
- [x] `pages/life/weather_dashboard.html` — navbar 삽입 + 전체 다크 테마 재설계
  - CSS 전체 교체 (Absolute Black 기반)
  - Chart.js grid/tick 색상 다크 처리
  - `makeCellHtml()` JS 인라인 컬러 전부 다크 처리
  - 강수 배경색 밝은 파란색 → 어두운 네이비 계열로 톤다운
- [x] `pages/bible/summary/israel-kings-timeline.html` — navbar 삽입 + 전체 다크 테마 재설계
  - body 고정 높이 구조에 맞게 navbar `position:relative;flex-shrink:0` 처리
  - TOP/BOTTOM 버튼은 `#sarea` 내부 스크롤 대상
- [x] 샘플 파일 삭제 (`sample-1,2,3.html`, `pwa_generator.html`)

---

## 다음 작업 항목

- [ ] `israel-kings-timeline.html` — 모바일 반응형 검토 (현재 고정 높이 레이아웃)
- [ ] 새 카테고리 추가 시 `pages/<category>/` 폴더 아래 `CLAUDE.md`/`LOG.md`/`HANDOFF.md` 파일셋 생성
- [ ] 향후 추가 예정 페이지: `bible/maps/`, `bible/prophecy/` 등

---

## 디자인 토큰 빠른 참조

| 항목 | 값 |
|---|---|
| 배경 (Absolute Black) | `#000000` |
| 서피스 1 | `#181818` |
| 서피스 2 | `#202020` |
| 서피스 3 | `#313131` |
| Lamborghini Gold | `#FFC000` |
| Ash (보조 텍스트) | `#7D7D7D` |
| navbar 높이 | `44px` (모바일 `40px`) |
| border-radius | `0px` |

CSS 전체 코드는 `CLAUDE.md` 참조.

---

## 강수 배경색 (weather_dashboard 전용)

| 강수량 | 배경색 |
|---|---|
| 약한 비 1–5mm | `#0a1c33` |
| 보통 비 5–15mm | `#0b2847` |
| 강한 비 15mm+ | `#0d3464` |
