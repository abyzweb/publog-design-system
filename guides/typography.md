# 타이포그래피

## 기본 서체

| 서체 | 사용처 | Google Fonts 링크 |
|------|--------|-----------------|
| **Montserrat** | 영문 전용 — 로고, GNB, 가격, 뱃지, 숫자 강조 | weights: 400·600·700·800·900 |
| **Noto Sans KR** | 한글 본문, 상품명, 설명 전반 | weights: 300·400·500·700 |
| **GSB** | 이벤트 배너·시즌 특별 프로모션 타이틀에만 한정 사용 | — |

## Google Fonts 임포트

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,600;0,700;0,800;0,900;1,400&family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
```

## 타입 스케일

| 사용처 | 서체 | 크기 | 굵기 | 기타 |
|--------|------|------|------|------|
| H1 · 영문 대타이틀 | Montserrat | 48px+ | 900 | letter-spacing: -1.5px |
| H2 · 섹션 타이틀 | Montserrat | 28–32px | 800 | — |
| H3 · 상품명 | Noto Sans KR | 16–20px | 700 | — |
| Body · 본문 | Noto Sans KR | 13–14px | 400 | — |
| Price · 가격 | Montserrat | 18–24px | 800 | 반드시 `~` 포함 |
| GNB 메뉴 | Montserrat | 13px | 400 | letter-spacing: 0 |
| Caption · 주석 | Noto Sans KR | 10–12px | 300 | color: #999 |

## body 기본 설정

```css
body {
  font-family: 'Noto Sans KR', sans-serif;
  color: #333333;
  line-height: 1.6;
}

/* 영문·숫자 강조 */
.en, .num { font-family: 'Montserrat', sans-serif; }
```

## 사용 원칙

- 영문·숫자는 Montserrat 우선 적용
- 이벤트 배너 외 GSB 사용 금지
- 가격 표기 시 Montserrat 800 + `~` 기호 필수
