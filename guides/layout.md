# 레이아웃 & 그리드

## 핵심 수치

| 항목 | 값 |
|------|-----|
| 콘텐츠 최대 너비 | `1200px` (margin: 0 auto) |
| Viewport 고정 너비 | `1300px` (meta viewport) |
| 헤더 총 높이 | `200px` |
| GNB 드롭다운 높이 | `570px` · z-index: 9999 (권고) |
| 기본 여백 단위 | 4px 배수 원칙 (8·16·24·32·48px) — 컴포넌트 내부 12·14·20px 허용 |

## border-radius 규칙

| 요소 | radius |
|------|--------|
| 버튼 (기본) | `8px` |
| 카드 | `12px` |
| 알약형 (태그·뱃지) | `9999px` |
| 입력 필드 | `4px` |
| 코드 입력창 | `16px` |

## 공통 컨테이너

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}
```

## 페이지 섹션 구조

```
HEADER — 로고 + GNB · 총 높이 200px
GNB 2Depth 드롭다운 — 570px
메인 배너 / 이벤트 배너 — 전폭 또는 1200px
퀵메뉴 아이콘 바
콘텐츠 섹션들 (--belief 배경으로 구분)
FOOTER
```

## HTML 보일러플레이트

새 페이지 시작 시 이 코드를 베이스로 사용합니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>페이지 제목</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,600;0,700;0,800;0,900;1,400&family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  /* ── 브랜드 6색 ── */
  --trendy:    #222450;
  --friendly:  #FFCE2D;
  --clear:     #FFFFFF;
  --belief:    #F0F1F6;
  --stability: #111111;
  --attention: #515382;

  /* ── 보조 컬러 ── */
  --sky:    #159FDA;
  --red:    #FF4040;
  --orange: #FF5400;
  --purple: #7B42F6;

  /* ── 텍스트 & 테두리 ── */
  --text-body:  #333333;
  --text-muted: #777777;
  --text-light: #AAAAAA;
  --border:     #E4E5EC;

  /* ── 그레이 스케일 ── */
  --gray-text: #666666;
  --gray-hint: #999999;
  --gray-line: #CCCCCC;

  /* ── 배지 컬러 ── */
  --badge-new: #FF8F17;
  --badge-hot: #E5362C;

  /* ── 버튼 hover ── */
  --trendy-hover:    #3a3f7a;
  --sky-hover:       #0092c0;
  --friendly-hover:  #f0c000;
  --btn-make-hover:  #4e58c2;

  /* ── 배경 ── */
  --paper: #FAFAF7;  /* 페이지 기본 배경 */

  /* ── 퍼블코드 ── */
  --group-purple-soft: #ECEEFF;
  --radius: 12px;

  /* ── D-day ── */
  --dday-warn-bg:    #fffbeb;
  --dday-warn-tx:    #b45309;
  --dday-urgent-bg:  #fff1f2;
  --dday-urgent-tx:  #e11d48;

  /* ── 소셜 버튼 ── */
  --naver:      #1ec800;
  --kakao:      #FEE500;
  --kakao-text: #3C1E1E;
}

body {
  font-family: "Montserrat", "YoonGothicPro760", sans-serif;
  background: var(--paper);
  color: var(--text-body);
  line-height: 1.6;
}

.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.en, .num  { font-family: 'Montserrat', sans-serif; }
</style>
</head>
<body>

<!-- 여기에 내용 작성 -->

</body>
</html>
```

## 로고 규격

| 구분 | URL |
|------|-----|
| 기본 로고 (흰색·밝은 배경) | `https://www.publog.co.kr/main_2025/img/logo.png?t=1` |
| 역상 로고 (어두운 배경 `#222450`) | `https://www.publog.co.kr/main_2025/img/logo_w.png?t=1` |

- 헤더 내 너비: `130px`
- 최소 여백: 로고 외곽 상하좌우 16px 이상
- 로고는 반드시 위 URL에서 불러오세요. 이미지를 직접 그리거나 텍스트로 대체하지 마세요.
- 복잡한 사진 위 직접 배치 금지 — 반투명 오버레이 필요
