# LOG — pages/life

## 2026-06-15
**파일:** `weather_dashboard.html` → v6.0 릴리스

- Nominatim(OpenStreetMap) 지오코딩으로 교체 — 한국 주소 정확도 개선, 북한 지명 오류 해결
- 관심 지역 즐겨찾기 + 마지막 위치 localStorage 영구 저장
- 과거 데이터 기본값 3년 → 5년 변경
- Gemini API 자동 폴백 구현 (gemini-2.5-flash-lite → 2.0-flash-001 → 2.5-flash)
- AI 예측 방식(통계/API), 제공사(Claude/Gemini) 선택 새로고침 후에도 유지
- filter-panel `position:relative` 인라인 스타일 제거 → navbar 아래 44px 검은 간격 버그 수정
- 제공사 설정 복원 순서 버그 수정 (loadSettings 초기화 중 apiProvider가 "claude"로 덮어써지던 문제)
