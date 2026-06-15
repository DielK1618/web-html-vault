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

**파일:** `weather_dashboard.html` → v6.1

- 모바일 필터 패널 접기/펼치기 토글 (☰/✕ 햄버거 버튼, filter-content max-height 전환)
- 쿼리바 신설: 토글과 무관하게 항상 표시, 📍 지역 / 📅 기간 / 📊 연도 / 모드 칩 + 조회 버튼
- 필터 콘텐츠 내부 구분선 제거, 쿼리바~KPI~범례 영역 경계선 통일
- KPI바 중복 칩 제거 (쿼리바로 일원화)
- 햄버거 버튼 왼쪽 정렬, 버전 뱃지 오른쪽 정렬

**파일:** `weather_dashboard.html` → v6.2

- 기온 차트: 라인 → 캔들차트 (floating bar + 심지 플러그인)
  - 몸통: amTempMax~pmTempMax / 심지: tempMin~tempMax
- 선택 모드 버튼 추가, 독립 토글 방식
- 강수량 차트 연도 연동 통합 (applySelection)

**파일:** `weather_dashboard.html` → v6.3

- 기온 캔들차트 단순화: [tempMin, tempMax] 범위 박스만 표시 (심지 제거)
- 선택 모드 버튼 제거 — 범주 클릭으로 직접 토글
- toggleItem() _selMode 가드 제거 → 클릭 즉시 동작

**파일:** `weather_dashboard.html` → v6.4

- 차트 토글 버그 수정: chart.update('none') → chart.update() (Chart.js 4.4.1 색상 미갱신 문제)
- toggleItem() 솔로 선택 방식 도입:
  전체 활성 시 클릭 → 해당 항목만 ON, 나머지 dim
  솔로 상태에서 같은 항목 클릭 → 전체 복원
  혼합 상태 → 개별 토글
- _allItems Set 추가로 전체/솔로 상태 판별
- 데이터셋 type:'bar' 불필요 속성 제거
