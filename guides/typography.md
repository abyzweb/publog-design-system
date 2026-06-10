# 타이포그래피

## 기본 서체

| 서체 | 역할 | 웨이트 |
|------|------|--------|
| **YoonGothicPro760** | 한글 메인 — 본문·상품명·메뉴·설명 전반 | 720 / 740 / **760** / 780 시리즈 |
| **Montserrat** | 영문 보조 — 로고, GNB, 가격, 뱃지, 숫자 강조 | 400 / 600 / 700 / 800 / 900 (Google Fonts) |
| **GSB (지마켓산스Bold)** | 이벤트 전용 — 이벤트 배너·시즌 특별 프로모션 타이틀에만 한정 사용 | Bold |

## 전체 폰트 스택

```css
font-family: "Montserrat", "YoonGothicPro760", sans-serif;
```

## Google Fonts 임포트

```css
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+KR:100,300,400,500,700,900&subset=korean');
@import url('https://fonts.googleapis.com/css?family=Montserrat:300,400,500,600,700,800,900');
```

## 윤고딕 700시리즈 — @font-face

사내 서버 폰트 경로 기준 (외부 페이지는 Noto Sans KR로 대체)

```css
@font-face {
  font-family: "YoonGothicPro720";
  font-style: normal; font-weight: normal; font-display: swap;
  src: url("/include/fonts/woff/YoonGothicPro720.woff2") format("woff2"),
       url("/include/fonts/woff/YoonGothicPro720.woff") format("woff"),
       url("/include/fonts/eot/YoonGothicPro720.eot?") format("eot");
}
@font-face {
  font-family: "YoonGothicPro740";
  font-style: normal; font-weight: normal; font-display: swap;
  src: url("/include/fonts/woff/YoonGothicPro740.woff2") format("woff2"),
       url("/include/fonts/woff/YoonGothicPro740.woff") format("woff"),
       url("/include/fonts/eot/YoonGothicPro740.eot?") format("eot");
}
@font-face {
  font-family: "YoonGothicPro760";
  font-style: normal; font-weight: normal; font-display: swap;
  src: url("/include/fonts/woff/YoonGothicPro760.woff2") format("woff2"),
       url("/include/fonts/woff/YoonGothicPro760.woff") format("woff"),
       url("/include/fonts/eot/YoonGothicPro760.eot?") format("eot");
}
@font-face {
  font-family: "YoonGothicPro780";
  font-style: normal; font-weight: normal; font-display: swap;
  src: url("/include/fonts/woff/YoonGothicPro780.woff2") format("woff2"),
       url("/include/fonts/woff/YoonGothicPro780.woff") format("woff"),
       url("/include/fonts/eot/YoonGothicPro780.eot?") format("eot");
}
```

## 지마켓 산스 — @font-face

```css
/* Light */
@font-face {
  font-family: 'GSL';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansLight.woff') format('woff');
  font-weight: normal; font-style: normal; font-display: swap;
}
/* Medium */
@font-face {
  font-family: 'GSM';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansMedium.woff') format('woff');
  font-weight: normal; font-style: normal; font-display: swap;
}
/* Bold */
@font-face {
  font-family: 'GSB';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2001@1.1/GmarketSansBold.woff') format('woff');
  font-weight: normal; font-style: normal; font-display: swap;
}
```

## 타입 스케일

| 사용처 | 서체 | 크기 | 굵기 | 기타 |
|--------|------|------|------|------|
| H1 · 영문 대타이틀 | Montserrat | 48px+ | 900 | letter-spacing: -1.5px |
| H2 · 섹션 타이틀 | Montserrat | 28–32px | 800 | — |
| H3 · 상품명 | YoonGothicPro760 | 16–20px | 700 | — |
| Body · 본문 | YoonGothicPro760 | 13–14px | 400 | — |
| Price · 가격 | Montserrat | 18–24px | 800 | 반드시 `~` 포함 |
| GNB 메뉴 | Montserrat | 13px | 400 | letter-spacing: 0 |
| Caption · 주석 | YoonGothicPro760 | 10–12px | 300 | color: #999 |

## body 기본 설정

```css
body {
  font-family: "Montserrat", "YoonGothicPro760", sans-serif;
  color: #333333;
  line-height: 1.6;
}

/* 영문·숫자 강조 */
.en, .num { font-family: 'Montserrat', sans-serif; }
```

## 사용 원칙

- 한글 본문·상품명·설명은 YoonGothicPro760 우선 (외부 페이지는 Noto Sans KR로 대체)
- 영문·숫자는 Montserrat 우선 적용
- 이벤트 배너 외 GSB 사용 금지
- 가격 표기 시 Montserrat 800 + `~` 기호 필수
