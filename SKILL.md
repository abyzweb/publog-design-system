---
name: brandguide-publog
description: '"퍼블로그 디자인 시스템" 입력 시 활성화. 퍼블로그(publog.co.kr) 웹 디자인 표준 적용. HTML 수정·신규 컴포넌트 생성·가이드 업데이트 지원.'
---

<!-- 테스트 시: name을 brandguide-publog-test 로 변경 -->

# 퍼블로그 디자인 시스템

퍼블로그(publog.co.kr) 웹 디자인 표준을 적용해 HTML을 만들거나 수정하는 스킬입니다.

**SKILL_VER:** `v1.5.1`  <!-- 배포 때마다 guides/VERSION과 함께 갱신 -->

## 시작 시 버전 자가 점검 (1회)
첫 디자인 요청을 받았을 때 **한 번만** 수행한다 (이후 반복 안 함):
1. WebFetch — `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/VERSION`
2. 받은 최신 버전이 위 **SKILL_VER**와 **다르면**(= 이 스킬이 낡음) 사용자에게 한 번 안내:
   > ⚠️ 이 스킬이 GitHub 최신 파일과 **불일치**해요 — 설치본 `[SKILL_VER]` / 최신 `[받은 값]`.
   > 최신 스킬 파일로 **업데이트가 필요해요. 웹팀에 스킬 업데이트를 요청**해 주세요.
   > (작업은 계속할 수 있지만 일부 규칙이 옛 버전일 수 있어요.)
3. 같으면 조용히 진행. **WebFetch 실패 시** 점검을 건너뛰고 진행한다(작업을 막지 않음).

## "스킬체크" — 수동 동기화 검증 (명령)
사용자가 `스킬체크`(별칭 `스킬검증`)라고 입력하면, GitHub 최신과 일치하는지 **명시적으로 확인해 보고**한다 (일치할 때도 분명히 답함):
1. WebFetch — `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/VERSION`
2. 받은 값과 위 **SKILL_VER**를 비교해 결과 안내:
   - **일치** → "✅ 이 스킬은 최신이에요 — 설치본 `[SKILL_VER]` = GitHub `[받은 값]`. 동기화 OK."
   - **불일치** → "❌ 불일치 — 설치본 `[SKILL_VER]` / 최신 `[받은 값]`. 최신 스킬로 업데이트가 필요해요. **웹팀에 스킬 업데이트를 요청**해 주세요."
   - **WebFetch 실패** → "⚠️ GitHub 버전을 못 불러왔어요(네트워크·URL 확인). 잠시 후 다시 시도해 주세요."

---

## 브랜드 컬러 (CSS 변수명)

```css
--trendy:    #222450  /* 헤더·버튼 배경·텍스트 강조 — 가장 지배적, 교체 불가 */
--friendly:  #FFCE2D  /* CTA·이벤트·친근한 포인트 */
--clear:     #FFFFFF  /* 카드 배경·팝업 바탕 */
--belief:    #F0F1F6  /* 섹션 구분·소프트 컨테이너 */
--stability: #111111  /* 본문 강조 텍스트 */
--attention: #515382  /* GNB 호버·포인트 텍스트 */
```

**보조:** `--sky: #159FDA` · `--red: #FF4040` · `--orange: #FF5400` · `--purple: #7B42F6`  
**텍스트:** `--text-body: #333` · `--text-muted: #777` · `--border: #E4E5EC`

---

## 폰트 & 레이아웃

- **영문·숫자:** Montserrat (weights: 400·600·700·800·900)
- **한글·본문:** Noto Sans KR (weights: 300·400·500·700)
- **이벤트 배너 한정:** GSB (이벤트 배너·시즌 프로모션 타이틀에만 사용, 이외 금지)
- **컨테이너 최대 너비:** 1200px (margin: 0 auto · padding: 0 24px)
- **여백 단위:** 4px 배수 원칙 (8·16·24·32·48px) — 컴포넌트 내부 12·14·20px 허용
- **border-radius:** 기본 버튼 8px · 액션 버튼(장바구니·주문) 4px · 카드 12px · 알약형 9999px · 코드 입력 16px

### 타입 스케일

| 사용처 | 서체 | 크기 | 굵기 | 기타 |
|--------|------|------|------|------|
| H1 · 영문 대타이틀 | Montserrat | 48px+ | 900 | letter-spacing: -1.5px |
| H2 · 섹션 타이틀 | Montserrat | 28–32px | 800 | — |
| H3 · 상품명 | Noto Sans KR | 16–20px | 700 | — |
| Body · 본문 | Noto Sans KR | 13–14px | 400 | — |
| Price · 가격 | Montserrat | 18–24px | 800 | 반드시 `~` 포함 |
| GNB 메뉴 | Montserrat | 13px | 400 | letter-spacing: 0 |
| Caption · 주석 | Noto Sans KR | 10–12px | 300 | color: #999 |

### 로고

| 구분 | URL |
|------|-----|
| 기본 로고 (밝은 배경) | `https://www.publog.co.kr/main_2025/img/logo.png` |
| 역상 로고 (어두운 배경) | `https://www.publog.co.kr/main_2025/img/logo_w.png` |

- 헤더 너비: `130px` · 최소 여백: 상하좌우 16px 이상
- 복잡한 사진 위 직접 배치 금지 — 반투명 오버레이 필요

### 페이지 섹션 구조

```
HEADER — 로고 + GNB · 총 높이 200px
GNB 2Depth 드롭다운 — 570px · z-index: 9999
메인 배너 / 이벤트 배너 — 전폭 또는 1200px
퀵메뉴 아이콘 바
콘텐츠 섹션들 (--belief 배경으로 구분)
FOOTER
```

---

## HTML 시작 템플릿

새 HTML 생성 시 항상 아래 보일러플레이트를 베이스로 사용:

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
  --trendy: #222450; --friendly: #FFCE2D; --clear: #FFFFFF;
  --belief: #F0F1F6; --stability: #111111; --attention: #515382;
  --sky: #159FDA; --red: #FF4040; --orange: #FF5400; --purple: #7B42F6;
  --text-body: #333333; --text-muted: #777777; --text-light: #aaaaaa; --border: #E4E5EC;
  --badge-new: #FF8F17; --badge-hot: #E5362C;
  --naver: #1ec800; --kakao: #FEE500; --kakao-text: #3C1E1E;
  --dday-warn-bg: #FFF3CD; --dday-warn-tx: #856404;
  --dday-urgent-bg: #FFE5E5; --dday-urgent-tx: #DC3545;
  --trendy-hover: #3a3f7a; --sky-hover: #0092c0; --friendly-hover: #f0c000;
  --group-purple-soft: #ECEEFF;  /* 퍼블코드 그룹 배지·배경 */
  --gray-text: #666666; --gray-hint: #999999; --gray-line: #cccccc;
  --radius: 12px;  /* 카드 기본 border-radius */
}
body { font-family: 'Noto Sans KR', sans-serif; color: var(--text-body); line-height: 1.6; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
.en, .num { font-family: 'Montserrat', sans-serif; }
</style>
</head>
<body>
<!-- 내용 -->
</body>
</html>
```

---

## 첫 응답 안내

대화에서 HTML 생성·수정 요청을 처음 받았을 때 **한 번만** 아래 내용을 먼저 안내한다:

---
퍼블로그 브랜드 가이드를 기반으로 HTML을 만들어 드릴게요.

색상·폰트·여백 같은 규칙은 가이드대로 적용되지만,
레이아웃 배치나 디자인 느낌은 예상과 다를 수 있어요.

결과물을 보고 "이 부분이 이상해요", "좀 더 ○○하게 해줘" 처럼
구체적으로 말씀해 주시면 바로 수정할게요.
---

두 번째 요청부터는 이 안내를 반복하지 않는다.

---

## 작업 규칙

1. 브랜드 변수 외 임의 색상 사용 금지
2. 헤더·주요 버튼 배경은 반드시 `--trendy (#222450)`
3. 영문·숫자 강조는 Montserrat 적용
4. 컨테이너 최대 너비 1200px 유지
5. 여백은 4px 배수만 사용
6. HTML 생성 완료 후 → 파일로 다운로드할 수 있도록 전체 코드 제공

---

## 디자인 원칙

- AI 스러운 디자인 금지 (보라 그라데이션, Inter 폰트, 뻔한 카드 레이아웃)
- 명확한 디자인 컨셉을 먼저 정하고 코딩 시작
- 퍼블로그 톤 기준: `--trendy` 기반의 신뢰감 있는 레이아웃 + `--friendly` 포인트

---

## 컴포넌트 가이드 로딩

요청 유형에 따라 아래 URL을 **WebFetch로 불러온 뒤** 해당 내용을 기준으로 HTML을 생성한다.

| 요청 유형 | 불러올 URL |
|-----------|-----------|
| 색상·팔레트 관련 | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/colors.md` |
| 폰트·텍스트 스타일 | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/typography.md` |
| 레이아웃·간격·컨테이너 | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/layout.md` |
| 버튼·검색·카드·GNB 등 일반 컴포넌트 | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/components.md` |
| 퍼블코드 전용 컴포넌트 (SubTab·CodeChip·PublCard 등) | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/publog-code.md` |
| 아이콘·SVG·아이콘 라이브러리 | `https://raw.githubusercontent.com/abyzweb/publog-design-system/main/guides/icons.md` |

- 여러 유형이 섞인 요청이면 해당 파일을 모두 불러온다
- 불러온 내용이 이 파일의 내용과 충돌하면 **불러온 파일을 우선**한다

---

## 가이드 미등록 컴포넌트 처리

HTML 생성 시 위 컴포넌트 가이드와 대조합니다.

**가이드에 없는 컴포넌트가 포함된 경우:**
퍼블로그 톤으로 최대한 맞춰 생성하고, 아래 형식으로 안내합니다:

```
생성 완료! 아래 컴포넌트는 공식 가이드에 없어서 퍼블로그 톤으로 최대한 맞춰 생성했습니다.
UXUI 팀 가이드 추가 요청 양식을 미리 작성했습니다. 확인 후 수정해 주세요:

페이지명: [작업한 페이지 이름]
요청자: [대화에서 파악된 이름 또는 빈칸]
요청 컴포넌트 목록:
  - 배너 (10~35번 줄) — 메인 상단 프로모션용
  - 비디오 섹션 (80~115번 줄) — 상품 소개 영상 삽입
  [가이드 미등록 컴포넌트 전체 나열]

수정할 내용이 있으면 말씀해 주세요.
작업이 끝나면 '작업끝'을 입력해 주세요.
```

---

## "작업끝" 키워드 처리

사용자가 `작업끝`을 입력하면 아래 두 가지 중 선택지를 제시합니다:

```
작업이 완료됐습니다! 다음 중 선택해 주세요:

A. 웹팀에 검수 요청하기
   → 완성된 HTML 파일을 해당 웹팀에 검수 요청해 주세요. 해당 프로젝트 노션 경로에 업로드해 주시면 돼요.

B. 작업 마치기
   → 완성된 HTML 코드를 아래에 제공합니다. 복사해서 .html 파일로 저장하세요.
```
