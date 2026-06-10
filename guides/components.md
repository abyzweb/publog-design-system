# 컴포넌트 스펙

공식 등록된 컴포넌트 목록입니다. 스킬이 HTML 생성 시 이 목록과 대조합니다.
퍼블코드 전용 컴포넌트는 `publog-code.md`를 참조하세요.

---

## 버튼

### 기본 버튼 5종

| 버튼명 | 클래스 | 배경 | 텍스트 | hover |
|--------|--------|------|--------|-------|
| 주문하기 | `.btn-primary` | `var(--trendy)` | `#fff` | `#3a3f7a` |
| 바로구매 | `.btn-sky` | `var(--sky)` | `#fff` | `#0092c0` |
| 할인쿠폰 | `.btn-yellow` | `var(--friendly)` | `var(--trendy)` | `#f0c000` |
| 담아두기 | `.btn-outline` | 투명 · border `var(--trendy)` | `var(--trendy)` | bg `var(--trendy)` · color `#fff` |
| 샘플신청 | `.btn-ghost` | 투명 · border `var(--border)` | `var(--text-muted)` | border `#aaa` · color `#444` |

```css
/* 공통 */
.btn-primary, .btn-sky, .btn-yellow, .btn-outline, .btn-ghost {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 11px 24px;
  border-radius: 8px;
  font-size: 13px;
  font-weight: 700;
  border: none;
  cursor: pointer;
  font-family: 'Noto Sans KR', sans-serif;
}

.btn-primary  { background: var(--trendy);   color: #fff; }
.btn-sky      { background: var(--sky);       color: #fff; }
.btn-yellow   { background: var(--friendly);  color: var(--trendy); }
.btn-outline  { background: transparent; color: var(--trendy); border: 1.5px solid var(--trendy); }
.btn-ghost    { background: transparent; color: var(--text-muted); border: 1.5px solid var(--border); }

.btn-primary:hover  { background: var(--trendy-hover); }
.btn-sky:hover      { background: var(--sky-hover); }
.btn-yellow:hover   { background: var(--friendly-hover); }
.btn-outline:hover  { background: var(--trendy); color: #fff; }
.btn-ghost:hover    { border-color: #aaa; color: #444; }
```

```html
<button class="btn-primary">주문하기</button>
<button class="btn-sky">바로구매</button>
<button class="btn-yellow">할인쿠폰</button>
<button class="btn-outline">담아두기</button>
<button class="btn-ghost">샘플신청</button>
```

### 장바구니 영역 버튼

실제 장바구니·주문 페이지에서 사용하는 버튼으로 `border-radius: 4px` 적용.

```css
.btn-delete     { height: 44px; padding: 0 24px; background: #e9e9e9; color: #888; border: none; border-radius: 4px; font-size: 13px; font-weight: 500; cursor: pointer; }
.btn-multi      { height: 44px; padding: 0 20px; background: #fff; color: #333; border: 1px solid #ccc; border-radius: 4px; font-size: 13px; font-weight: 500; cursor: pointer; }
.btn-share-cart { height: 44px; padding: 0 24px; background: #fff; color: var(--trendy); border: 1px solid var(--trendy); border-radius: 4px; font-size: 13px; font-weight: 700; cursor: pointer; }
.btn-order-cart { height: 44px; padding: 0 40px; background: var(--trendy); color: #fff; border: none; border-radius: 4px; font-size: 13px; font-weight: 700; cursor: pointer; }

.btn-delete:hover     { background: #d5d5d5; }
.btn-multi:hover      { background: #f5f5f5; border-color: #aaa; }
.btn-share-cart:hover { background: var(--belief); }
.btn-order-cart:hover { background: #3a3f7a; }
```

```html
<button class="btn-delete">선택삭제</button>
<button class="btn-multi">다중배송 신청하기</button>
<button class="btn-share-cart">공유하기</button>
<button class="btn-order-cart">주문하기</button>
```

### 상품 상세 페이지 버튼

높이 60px · border-radius 없음 (직각)

```css
.btn-make   { height: 60px; padding: 0 32px; background: #262853; color: #fff; border: none; font-size: 15px; font-weight: 700; cursor: pointer; }
.btn-pdf    { height: 60px; padding: 0 32px; background: #999; color: #fff; border: none; font-size: 15px; font-weight: 700; cursor: pointer; }
.btn-basket { height: 60px; width: 70px; background: #ccc; color: #fff; border: none; font-size: 12px; font-weight: 700; cursor: pointer; }

.btn-make:hover { background: var(--btn-make-hover); }
.btn-pdf:hover  { background: #b3b3b3; }
```

```html
<button class="btn-basket">🛒</button>
<button class="btn-pdf">PDF 업로드</button>
<button class="btn-make">디자인 선택하기</button>
```

---

## 검색 컴포넌트

헤더 GNB 내 검색창. 높이 40px · border `1px solid var(--trendy)`.

```css
.search-wrap {
  position: relative;
  display: flex;
  align-items: center;
  height: 40px;
  border-radius: 4px;
  border: 1px solid var(--trendy);
  background: #fff;
}

.search-input {
  flex: 1;
  height: 100%;
  padding: 0 40px 0 12px;
  border: none;
  outline: none;
  font-size: 11.5px;
  font-family: 'Noto Sans KR', sans-serif;
  color: var(--stability);
  background: transparent;
}

.search-input::placeholder { color: #999; }

.search-btn {
  position: absolute;
  right: 5px;
  top: 50%;
  transform: translateY(-50%);
  width: 28px;
  height: 28px;
  border: none;
  background: transparent;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

```html
<div class="search-wrap">
  <input class="search-input" type="text" placeholder="상품을 검색하세요">
  <button class="search-btn">🔍</button>
</div>
```

---

## 입력 필드 (Field)

```css
.field-input {
  width: 100%;
  height: 48px;
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 0 14px;
  font-size: 14px;
  font-family: 'Noto Sans KR', sans-serif;
  color: var(--stability);
  background: #fff;
  outline: none;
  box-sizing: border-box;
}

.field-input:focus { border-color: var(--trendy); }
.field-input::placeholder { color: var(--text-muted); }
```

```html
<input class="field-input" type="text" placeholder="내용을 입력하세요">
```

---

## 카드

```css
.card {
  background: #fff;
  border-radius: 12px;
  border: 1px solid var(--border);
  overflow: hidden;
}

/* 선택적 그림자 */
.card-shadow { box-shadow: 0 4px 16px rgba(0,0,0,0.08); }

/* 섹션 구분 배경 */
.card-belief { background: var(--belief); }
```

```html
<div class="card">
  <!-- 카드 내용 -->
</div>
```

### 상품 카드

```css
.product-card { border: 1px solid var(--border); border-radius: 12px; overflow: hidden; background: #fff; }
.product-card-thumb { height: 140px; background: var(--belief); display: flex; align-items: center; justify-content: center; }
.product-card-body { padding: 12px 14px; }
.product-card-name { font-size: 13px; font-weight: 700; color: var(--stability); margin-bottom: 3px; }
.product-card-desc { font-size: 11px; color: var(--text-muted); margin-bottom: 8px; }
.product-card-price { font-family: 'Montserrat', sans-serif; font-size: 17px; font-weight: 800; color: var(--trendy); }
```

```html
<div class="product-card">
  <div class="product-card-thumb"><!-- 상품 이미지 --></div>
  <div class="product-card-body">
    <div class="product-card-name">상품명</div>
    <div class="product-card-desc">상품 설명</div>
    <div class="product-card-price">6,400원~</div>
  </div>
</div>
```

---

## 태그 & 뱃지

### 메뉴영역 말풍선 태그 (GNB 카테고리)

GNB 메뉴 항목 옆에 붙는 작은 태그. height 22px · border-radius 30px.

```css
.memo-tag {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 22px;
  padding: 0 10px;
  border-radius: 30px;
  font-size: 11px;
  font-weight: 700;
  color: #fff;
  white-space: nowrap;
}

.memo-tag-new    { background: var(--badge-new); }           /* #FF8F17 */
.memo-tag-hot    { background: var(--badge-hot); }           /* #E5362C */
.memo-tag-season { background: var(--trendy); }              /* #222450 */
.memo-tag-consult { background: #fff; color: var(--purple); box-shadow: inset 0 0 0 2px var(--purple); }
.memo-tag-quick   { background: #fff; color: var(--badge-hot); box-shadow: inset 0 0 0 2px var(--badge-hot); }
```

```html
<span class="memo-tag memo-tag-new">NEW</span>
<span class="memo-tag memo-tag-hot">HOT</span>
<span class="memo-tag memo-tag-season">SEASON</span>
<span class="memo-tag memo-tag-consult">상담</span>
<span class="memo-tag memo-tag-quick">빠른배송</span>
```

### GNB 드롭다운 상품리스트 태그

드롭다운 상품명 앞에 붙는 소형 태그. height 약 20px · border-radius 3px.

```css
.gnb-tag {
  display: inline-block;
  padding: 2px 7px;
  font-size: 10px;
  font-weight: 700;
  border-radius: 3px;
  font-family: 'Montserrat', sans-serif;
  line-height: 1.4;
}

.gnb-tag-hot     { background: #ff7373; color: #fff; }
.gnb-tag-new     { background: transparent; color: #ff4040; border: 1px solid #ff4040; }
.gnb-tag-upgrade { background: #ff7373; color: #fff; width: 22px; text-align: center; padding: 2px 0; }
```

```html
<span class="gnb-tag gnb-tag-hot">HOT</span>
<span class="gnb-tag gnb-tag-new">NEW</span>
<span class="gnb-tag gnb-tag-upgrade">UP</span>
```

### 상품 목록 인라인 배지

상품 카드·리스트에 붙는 배지. border-radius 3–4px.

```css
.badge {
  display: inline-block;
  padding: 3px 8px;
  border-radius: 3px;
  font-size: 10px;
  font-weight: 800;
}

.badge-coupon   { background: var(--trendy); color: #fff; padding: 3px 5px; font-size: 12px; }
.badge-outline  { background: transparent; color: var(--trendy); border: 1px solid var(--trendy); }
.badge-same-day { background: #e8f8f0; color: #1a8c4e; border-radius: 4px; }
.badge-quick    { background: var(--friendly); color: var(--trendy); border-radius: 4px; }
```

```html
<span class="badge badge-coupon">쿠폰</span>
<span class="badge badge-outline">NEW</span>
<span class="badge badge-same-day">당일출고</span>
<span class="badge badge-quick">빠른배송</span>
```

### 상품 배지 (PRODUCT BADGES)

상품 리스트·상세 페이지에 노출되는 원형 아이콘 배지. 한 상품에 최대 2개까지 조합 가능.

| 배지명 | 이미지 URL |
|--------|-----------|
| KC 인증 | `https://www.publog.co.kr/gnb/new/l_kc_mark.png?t=2` |
| 업계 최저가 | `https://stay10.publog.co.kr/gnb/new/l_low.png?t=1` |
| 번개배송 | `https://stay10.publog.co.kr/gnb/new/l_quick.png?t=1` |
| NEW DESIGN | `https://stay10.publog.co.kr/gnb/new/l_newdesign.png?t=1` |
| 귀도리컷팅 | `https://stay10.publog.co.kr/gnb/new/cutr_icon.png?t=1` |
| 대량구매 상담상품 | `https://stay10.publog.co.kr/gnb/new/l_designadvice_tag.png?t=1` |
| 디자인 대행신청 | `https://stay10.publog.co.kr/gnb/new/l_designapply_tag.png?t=1` |
| 2시 마감 당일출고 | `https://stay10.publog.co.kr/gnb/new/l_shipstoday_tag.png?t=1` |

모든 배지 이미지: `45×45px` · `object-fit: contain`

```html
<div style="display: flex; gap: 4px;">
  <img src="https://www.publog.co.kr/gnb/new/l_kc_mark.png?t=2" width="45" height="45" style="object-fit:contain" alt="KC인증">
  <img src="https://stay10.publog.co.kr/gnb/new/l_quick.png?t=1" width="45" height="45" style="object-fit:contain" alt="번개배송">
</div>
```

---

## 로고 시스템

### 공식 로고 3종

| 종류 | 이미지 경로 | 사용 배경 |
|------|------------|----------|
| Standard | `https://www.publog.co.kr/main_2025/img/logo.png?t=1` | 흰 배경 위 기본형 — 가장 많이 사용 |
| Bright background | `https://www.publog.co.kr/main_2025/img/logo.png?t=1` | 밝은/그레이 배경 — #F0F1F6 위 |
| Dark background | `https://www.publog.co.kr/main_2025/img/logo_w.png?t=1` | 어두운 배경 — #222450 위 역상 |

### 규격

| 항목 | 규격 |
|------|------|
| 헤더 내 너비 | `130px` (img width 기준) |
| 헤더 총 높이 | `200px` 내 배치 |
| OG/소셜 이미지 | `/main_img/publog_mobile_blue.png` |
| 금지 사항 | 복잡한 사진 위 직접 배치 금지 — 반투명 오버레이 필요 |
| 최소 여백 | 로고 외곽 상하좌우 16px 이상 |

---

## GNB 헤더 (PC)

3단 구조 — 유틸리티 바 / 메인 헤더 / GNB 카테고리 바

### 유틸리티 바 (상단)

- 배경: `#fff` · border-bottom: `1px solid rgba(0,0,0,0.06)`
- 높이: `34px` · 텍스트: `#555` · `11.5px`

### 메인 헤더

- 높이: `80px`
- 로고: `main_2025/img/logo.png` · width `130px`
- 검색창: height `40px` · border-radius `4px` · border `1px solid var(--trendy)`
- 검색 버튼: bg `var(--trendy)` · 흰색 아이콘

### GNB 카테고리 바

- 높이: `58px`
- 폰트: `14px 600` · `#333` · hover `var(--trendy)`

---

## 로그인 모달

| 항목 | 스펙 |
|------|------|
| 카드 배경 | `#fff` · border-radius `16px` |
| box-shadow | `0 32px 64px -16px rgba(0,0,0,0.22)` |
| 카드 너비 | `360px` |
| 입력 필드 | height `48px` · border `1px solid var(--border)` · border-radius `4px` · focus `var(--trendy)` |
| 로그인 버튼 | bg `var(--trendy)` · color `#fff` · height `52px` · border-radius `4px` |
| 카카오 버튼 | bg `var(--kakao)` · color `var(--kakao-text)` · height `52px` · border-radius `4px` |

```css
.login-modal {
  width: 360px;
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 32px 64px -16px rgba(0,0,0,0.28);
  padding: 40px 32px 32px;
}

.login-title {
  font-family: 'Montserrat', sans-serif;
  font-size: 17px;
  font-weight: 900;
  letter-spacing: 0.06em;
  color: var(--trendy);
  text-align: center;
  margin-bottom: 28px;
}

.login-field {
  width: 100%;
  height: 48px;
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 0 16px;
  font-size: 13.5px;
  font-family: 'Noto Sans KR', sans-serif;
  outline: none;
  margin-bottom: 10px;
}

.login-field:focus { border-color: var(--trendy); }

.login-btn {
  width: 100%;
  height: 52px;
  border-radius: 4px;
  border: none;
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
}

.login-btn-primary { background: var(--trendy); color: #fff; }
.login-btn-kakao   { background: var(--kakao);  color: var(--kakao-text); }

/* 소셜 로그인 아이콘 버튼 */
.social-btn {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: none;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.social-btn-naver  { background: var(--naver); }
.social-btn-apple  { background: #000; }
.social-btn-google { background: #fff; border: 1px solid #d9d9d9; }
```

```html
<div class="login-modal">
  <div class="login-title">WELCOME TO GOODS PLANET</div>
  <input class="login-field" type="text" placeholder="아이디">
  <input class="login-field" type="password" placeholder="비밀번호">
  <button class="login-btn login-btn-primary">로그인</button>
  <button class="login-btn login-btn-kakao">카카오로 시작하기</button>
  <div style="display: flex; justify-content: center; gap: 8px;">
    <button class="social-btn social-btn-naver"></button>
    <button class="social-btn social-btn-apple"></button>
    <button class="social-btn social-btn-google"></button>
  </div>
</div>
```

---

## 채널 & SNS 카드

온라인 판매 채널·SNS 링크를 그리드로 나열하는 섹션 컴포넌트.

```css
.sns-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 10px;
}

.sns-card {
  padding: 16px;
  border-radius: 12px;
  border: 1px solid var(--border);
  text-align: center;
  background: #fff;
}

.sns-icon {
  width: 45px;
  height: 45px;
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 10px auto 0;
  overflow: hidden;
}

.sns-name {
  font-size: 11px;
  font-weight: 700;
  color: var(--trendy);
  margin-top: 8px;
}

.sns-url {
  font-size: 9px;
  color: var(--text-muted);
  margin-top: 3px;
  word-break: break-all;
}
```

```html
<div class="sns-grid">
  <div class="sns-card">
    <div class="sns-icon"><!-- 아이콘 이미지 --></div>
    <div class="sns-name">KakaoTalk</div>
    <div class="sns-url">pf.kakao.com/_xbxmxhzE</div>
  </div>
  <div class="sns-card">
    <div class="sns-icon"><!-- 아이콘 이미지 --></div>
    <div class="sns-name">Instagram</div>
    <div class="sns-url">instagram.com/publog_official</div>
  </div>
</div>
```

---

## 모바일 하단 네비게이션

| 항목 | 스펙 |
|------|------|
| 배경 | `#fff` · 높이 `64px` |
| box-shadow | `0 -1px 0 rgba(0,0,0,0.06)` |
| 아이콘 | `24×24px` |
| 라벨 | `10px` |
| 활성 색상 | `var(--trendy)` |
| 비활성 색상 | `#999999` |

```css
.mobile-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: 64px;
  background: #fff;
  box-shadow: 0 -1px 0 rgba(0,0,0,0.06);
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.mobile-nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  color: #999;
  font-size: 10px;
  font-weight: 500;
}

.mobile-nav-item.active { color: var(--trendy); }

.mobile-nav-icon { width: 24px; height: 24px; }
```

```html
<nav class="mobile-nav">
  <div class="mobile-nav-item active">
    <img class="mobile-nav-icon" src="ico_home.png" alt="홈">
    <span>홈</span>
  </div>
  <div class="mobile-nav-item">
    <img class="mobile-nav-icon" src="ico_search.png" alt="검색">
    <span>검색</span>
  </div>
  <div class="mobile-nav-item">
    <img class="mobile-nav-icon" src="ico_cart.png" alt="장바구니">
    <span>장바구니</span>
  </div>
  <div class="mobile-nav-item">
    <img class="mobile-nav-icon" src="ico_my.png" alt="마이">
    <span>마이</span>
  </div>
</nav>
```

---

## Stat Card (통계 카드)

```css
.stat-card {
  border-radius: 12px;
  padding: 14px 16px;
  background: var(--belief);
}

.stat-value {
  font-family: 'Montserrat', sans-serif;
  font-size: 22px;
  font-weight: 800;
  color: var(--trendy);
}

.stat-label { font-size: 10.5px; color: #777; }

/* 강조 변형 */
.stat-card-accent { background: #eef2ff; }
.stat-card-accent .stat-value { color: var(--attention); }
```

```html
<div class="stat-card">
  <div class="stat-value">8</div>
  <div class="stat-label">공유한 코드</div>
</div>
<!-- D-day 강조 변형 -->
<div class="stat-card stat-card-accent">
  <div class="stat-value">D-14</div>
  <div class="stat-label">만료까지</div>
</div>
```

---

## D-day 배지

퍼블코드 서비스에서 주로 사용. 마감일 긴급도에 따라 색상이 달라집니다.

| 조건 | 배경 | 텍스트 |
|------|------|--------|
| D-day > 7 (여유) | `var(--belief)` | `var(--text-muted)` |
| D-day ≤ 7 (주의) | `var(--dday-warn-bg)` | `var(--dday-warn-tx)` |
| D-day ≤ 3 (긴급) | `var(--dday-urgent-bg)` | `var(--dday-urgent-tx)` |

```css
.dday-badge {
  display: inline-flex;
  align-items: center;
  height: 26px;
  padding: 0 12px;
  border-radius: 9999px;
  font-family: 'Montserrat', sans-serif;
  font-size: 11px;
  font-weight: 700;
}

.dday-safe    { background: var(--belief);          color: var(--text-muted); }
.dday-warn    { background: var(--dday-warn-bg);    color: var(--dday-warn-tx); }
.dday-urgent  { background: var(--dday-urgent-bg);  color: var(--dday-urgent-tx); }
```

```html
<span class="dday-badge dday-urgent">D-2</span>
<span class="dday-badge dday-warn">D-5</span>
<span class="dday-badge dday-safe">D-14</span>
```

---

## Step Indicator (다단계 진행 표시)

```css
.step-wrap {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 14px 0;
}

.step-label {
  font-family: 'Montserrat', sans-serif;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  color: var(--text-muted);
  white-space: nowrap;
}

.step-label em { color: var(--trendy); font-style: normal; }

.step-bar-track {
  flex: 1;
  height: 3px;
  border-radius: 9999px;
  background: rgba(0,0,0,0.06);
  overflow: hidden;
}

.step-bar-fill {
  height: 100%;
  border-radius: 9999px;
  background: var(--trendy);
  transition: width 300ms;
}

/* 완료 단계 */
.step-bar-fill.done { background: var(--purple); }

.step-name {
  font-size: 13px;
  font-weight: 600;
  color: var(--trendy);
  white-space: nowrap;
}
```

```html
<div class="step-wrap">
  <span class="step-label">STEP <em>1</em> / 3</span>
  <div class="step-bar-track">
    <div class="step-bar-fill" style="width: 33%;"></div>
  </div>
  <span class="step-name">상품 선택</span>
</div>
```

---

## Stepper (수량 조절)

```css
.stepper {
  display: inline-flex;
  align-items: center;
  gap: 4px;
}

.stepper-btn {
  width: 36px;
  height: 36px;
  border-radius: 9999px;
  border: 1px solid rgba(0,0,0,0.12);
  background: #fff;
  font-size: 18px;
  font-weight: 400;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.stepper-value {
  font-family: 'Montserrat', sans-serif;
  font-size: 15px;
  font-weight: 700;
  min-width: 40px;
  text-align: center;
}
```

```html
<div class="stepper">
  <button class="stepper-btn">−</button>
  <span class="stepper-value">1</span>
  <button class="stepper-btn">+</button>
</div>
```
