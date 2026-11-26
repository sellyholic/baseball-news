# KBO 야구 뉴스 (초등 야구팬용)

유튜브·쇼츠·광고·댓글 없이 **KBO 소식만** 읽을 수 있는 한 장짜리 웹페이지입니다.
휴대폰 홈 화면에 추가하면 앱 아이콘처럼 열립니다.

- 주소: https://sellyholic.github.io/baseball-news/
- 파일: `index.html` (모든 내용·디자인이 이 파일 하나에 들어 있습니다)

## 매일 새 소식으로 바꾸는 방법

`index.html`에서 아래 두 곳만 고치면 됩니다.

1. 맨 위 제목 근처의 날짜
   ```html
   <div class="date">📅 2026년 11월 27일 금요일</div>
   ```
2. `<main id="news">` 안의 기사 카드들 (`<article class="card" ...>` ~ `</article>`)

카드 하나의 모양:

```html
<article class="card" data-teams="두산 KIA">
  <div class="card-head"><span class="num">1</span><span class="team">두산</span></div>
  <h2>제목</h2>
  <p>설명</p>
  <div class="points">
    <h3>숫자로 보기</h3>
    <ul><li>내용</li></ul>
  </div>
  <p class="easy"><strong>쉽게 말하면</strong> — 내용</p>
  <div class="source"><span>출처</span><span>·</span><span>매체 (날짜)</span></div>
</article>
```

- `data-teams`에 팀 이름을 넣으면 위쪽 팀 버튼으로 걸러 볼 수 있습니다 (`KIA 두산 한화 SSG 삼성 LG KT 롯데 KBO`).
- 확인한 사실만 적고, 출처와 날짜를 카드 아래에 남깁니다.
- 영상·광고·외부 링크·댓글은 넣지 않습니다.

## 응원하는 팀 강조하기

`index.html` 아래쪽 스크립트에서 한 줄만 바꾸면 그 팀 기사가 맨 위로 올라오고 ⭐ 표시가 붙습니다.

```js
const FAVORITE_TEAM = "한화";
```

## 구성 파일

| 파일 | 설명 |
| --- | --- |
| `index.html` | 페이지 전체 (HTML + CSS + 아주 작은 자바스크립트) |
| `manifest.webmanifest` | 홈 화면에 추가할 때 쓰는 앱 정보 (이름, 색, 아이콘) |
| `sw.js` | 인터넷이 잠깐 끊겨도 마지막 화면이 열리게 하는 캐시 |
| `icon.svg`, `icon-192.png`, `icon-512.png`, `icon-180.png` | 앱 아이콘 |
| `.nojekyll` | GitHub Pages가 파일을 그대로 올리도록 하는 표시 |

## 휴대폰 홈 화면에 추가

- **안드로이드(Chrome)**: 주소를 연 뒤 오른쪽 위 ⋮ → **홈 화면에 추가**
- **아이폰(Safari)**: 아래 공유 버튼 → **홈 화면에 추가**

## 호스팅

GitHub Pages, `main` 브랜치 루트(`/`)에서 제공됩니다.
