# HANDOFF — pages/life

## 현재 상태
- `weather_dashboard.html` v6.4 — 정상 작동 중 (GitHub Pages 배포 완료)

## 주요 구조
- **지오코딩:** Nominatim API (`https://nominatim.openstreetmap.org/search`)
- **날씨 데이터:** Open-Meteo (archive + forecast 엔드포인트)
- **AI 예측:** 통계 예측(무료) / AI API (Claude 또는 Gemini 자동 폴백)
- **localStorage 키:** `weather_favorites`, `weather_last_location`, `weather_years`, `weather_ai_mode`, `weather_api_provider`, `apiKey_claude`, `apiKey_gemini`

## 차트 구조 (v6.4)
- **기온 차트:** Chart.js bar, floating bar `[tempMin, tempMax]`, 연도별 색상 박스
- **강수량 차트:** Chart.js bar, 연도별 일 강수량
- **범주 토글:** `_activeItems` / `_allItems` Set으로 관리
  - 전체 활성 시 클릭 → 솔로 (해당 항목만 ON)
  - 솔로 상태에서 같은 항목 클릭 → 전체 복원
  - 혼합 상태 → 개별 토글

## 다음 작업 후보
- 기온/강수량 외 추가 차트 (습도, 풍속 등)
- 날씨 매트릭스 셀 상세 툴팁 개선
- 즐겨찾기 지역 간 비교 기능
