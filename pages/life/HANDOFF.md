# HANDOFF — pages/life

## 현재 상태
- `weather_dashboard.html` v6.0 — 정상 작동 중 (GitHub Pages 배포 완료)

## 주요 구조
- **지오코딩:** Nominatim API (`https://nominatim.openstreetmap.org/search`)
- **날씨 데이터:** Open-Meteo (archive + forecast 엔드포인트)
- **AI 예측:** 통계 예측(무료) / AI API (Claude 또는 Gemini 자동 폴백)
- **localStorage 키:** `weather_favorites`, `weather_last_location`, `weather_years`, `weather_ai_mode`, `weather_api_provider`, `apiKey_claude`, `apiKey_gemini`

## 다음 작업 후보
- 모바일 레이아웃 점검 (필터 패널, 날씨 셀)
- 차트 섹션 추가 또는 개선 (현재 matrix + chart-panel 기본 구조)
- 시간별 예보 표시 개선
