# HTML VAULT — Claude 작업 지침

## 프로젝트 개요
- **저장소**: `web-html-vault` (GitHub Pages: https://dielk1618.github.io/web-html-vault/)
- **루트 index**: `index.html` (Absolute Black `#000000`, DESIGN_Lamborghini.md 기준)
- **페이지 위치**: `pages/` 하위 카테고리 폴더에 작성

---

## 공통 Navbar 규칙

**모든 새 HTML 파일에는 반드시 공통 navbar를 `<body>` 최상단에 삽입한다.**

배경 색상에 관계없이 **단일 디자인** 사용 — Absolute Black `#000000`, Lamborghini Gold `#FFC000` 액센트.

---

### HTML

```html
<nav class="vault-nav">
  <a class="vault-logo" href="https://dielk1618.github.io/web-html-vault/index.html">
    HTML <span>VAULT</span>
  </a>
  <div class="vault-nav-btns">
    <a class="vbtn" href="https://dielk1618.github.io/web-html-vault/index.html">HOME</a>
    <div class="vsep"></div>
    <button class="vbtn" onclick="window.scrollTo({top:0,behavior:'smooth'})">TOP</button>
    <div class="vsep"></div>
    <button class="vbtn" onclick="window.scrollTo({top:document.body.scrollHeight,behavior:'smooth'})">BOTTOM</button>
  </div>
</nav>
```

### CSS

```css
.vault-nav{position:sticky;top:0;z-index:1000;display:flex;align-items:center;justify-content:space-between;padding:0 40px;height:44px;background:#000;border-bottom:1px solid #202020;font-family:'Inter',Roboto,'Helvetica Neue',Arial,sans-serif;}
.vault-logo{font-size:15px;font-weight:700;letter-spacing:.06em;text-transform:uppercase;color:#fff;text-decoration:none;display:flex;align-items:center;}
.vault-logo span{color:#FFC000}
.vault-nav-btns{display:flex;align-items:center}
.vbtn{padding:0 16px;height:44px;border:none;background:none;font-size:10px;font-weight:700;font-family:inherit;letter-spacing:.12em;text-transform:uppercase;color:#7D7D7D;cursor:pointer;text-decoration:none;display:inline-flex;align-items:center;transition:color .15s;}
.vbtn:hover{color:#FFC000}
.vsep{width:1px;height:16px;background:#202020;flex-shrink:0}
@media(max-width:600px){.vault-nav{padding:0 20px;height:40px}.vbtn{padding:0 10px;height:40px;font-size:9px}.vault-logo{font-size:13px}}
```

**디자인 토큰:**
- 배경: `#000000` (Absolute Black)
- 경계선: `#202020` (Charcoal)
- 로고 accent: `#FFC000` (Lamborghini Gold)
- 버튼 기본: `#7D7D7D` (Ash)
- 버튼 hover: `#FFC000`
- 높이: 44px (모바일 40px)
- border-radius: 0px

---

## 파일 관리 규칙

- 새 카테고리 폴더를 만들 때 해당 폴더에도 `CLAUDE.md`, `LOG.md`, `HANDOFF.md` 파일셋을 생성한다
- `LOG.md`에 작업 날짜·내용·파일 목록을 기록한다
- `HANDOFF.md`는 현재 상태 + 다음 작업 항목을 항상 최신으로 유지한다
- 언더스코어(`_`)로 시작하는 파일은 작업용이며 배포 대상이 아니다 — index.html 목록에서도 자동 제외됨

## 디자인 기본 스타일

새 HTML 파일의 색상, 타이포그래피, 간격 등 기본 스타일은 반드시 **`d:\CLOUD\OneDrive\DIEL_VAULT\DEVELOPMENT\Git\ref-design\DESIGN_Lamborghini.md`** 를 기준으로 한다.
작업 전 해당 파일을 먼저 읽고 정의된 디자인 토큰·컴포넌트 규칙을 준수한다.

## 반응형 디자인

모든 HTML 파일은 **모바일·태블릿·데스크톱** 멀티디바이스에서 정상적으로 사용 가능하도록 반응형으로 제작한다.

- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` 필수 포함
- 고정 px 폭 레이아웃 금지 — `max-width`, `%`, `clamp()`, `flex`, `grid` 활용
- 터치 타깃 최소 44×44px (버튼, 링크, 인터랙티브 요소)
- 브레이크포인트 기준: 모바일 `≤600px` / 태블릿 `601–1024px` / 데스크톱 `1025px+`
- 텍스트 크기는 `clamp()` 또는 `vw` 단위로 유동적으로 처리
- 가로 스크롤이 발생하지 않아야 한다

## 코딩 스타일

- HTML/CSS는 미니파이 스타일(한 줄 선언) 유지 — 기존 파일 패턴을 따른다
- 불필요한 주석 추가 금지
- 페이지 고유 `.home-btn` 등 기존 홈 버튼이 있으면 navbar 추가 시 제거한다
