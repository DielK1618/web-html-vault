# TROUBLESHOOTING.md — web-html-vault

오류 발생 시 이 문서를 먼저 확인한다. 해결책이 없으면 LOG.md / 웹 검색 순으로 진행하고, 해결 후 이 문서에 추가한다.

---

## GitHub Pages / 배포

### TS-H01 · 저장소명 변경 후 내부 링크 404

**증상**: 저장소 이름이 바뀐 후 페이지 간 링크 또는 리소스 경로가 404

**원인**: HTML 파일 내 절대 경로에 구 저장소명이 하드코딩되어 있음

**해결**: 전체 파일에서 구 URL 패턴 검색 후 일괄 교체

```powershell
# 구 URL 일괄 검색
Get-ChildItem -Recurse -Filter "*.html" | Select-String "html-vault" | Select Path, LineNumber
```

**과거 사례**: `html-vault` → `web-html-vault` 변경 시 발생 (2026-06-17)

---

### TS-H02 · HTML 파일 한글 깨짐 (BOM 문자)

**증상**: 브라우저에서 페이지 열면 상단에 `ï»¿` 문자 표시 또는 한글이 깨짐

**원인**: 파일이 UTF-8 with BOM으로 저장됨. GitHub Pages 또는 일부 브라우저에서 BOM을 잘못 해석

**해결**: BOM 없는 UTF-8로 재저장

```powershell
# BOM 제거
$content = Get-Content "파일.html" -Raw -Encoding UTF8
$utf8NoBOM = New-Object System.Text.UTF8Encoding $false
[System.IO.File]::WriteAllText("파일.html", $content, $utf8NoBOM)
```

---

## 레이아웃 / Navbar

### TS-H03 · `body { height:100dvh; overflow:hidden }` 구조에서 vault-nav 밀림

**증상**: `height:100dvh; overflow:hidden` + flex 레이아웃 페이지에 vault-nav 추가 시 콘텐츠 영역이 nav 뒤로 밀리거나 스크롤이 깨짐

**원인**: fixed/sticky nav가 flex 자식 요소로 포함되면 height 계산이 틀어짐

**해결**: vault-nav를 `position:relative; flex-shrink:0`으로 설정하고, 콘텐츠 영역을 `flex:1; overflow-y:auto`로 설정

```css
.vault-nav { position: relative; flex-shrink: 0; }
#main-content { flex: 1; overflow-y: auto; }
```

**과거 사례**: `israel-kings-timeline.html` 적용 시 발생 (2026-06-12)

---

## 디자인 시스템

### TS-H04 · Tailwind CDN 클래스와 커스텀 CSS 충돌

**증상**: Tailwind CDN 사용 시 커스텀 CSS 클래스가 Tailwind 기본값에 의해 덮어씌워짐

**원인**: Tailwind 기본 reset/utility가 커스텀 스타일보다 우선순위가 높거나 같음

**해결**: 커스텀 스타일을 `<style>` 태그에 `!important` 추가하거나, Tailwind `@layer` 사용. 또는 Tailwind CDN 완전 제거 후 순수 CSS로 구현 (이 프로젝트 기본 방향).
