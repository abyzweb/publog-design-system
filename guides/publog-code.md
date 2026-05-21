# 퍼블코드 전용 컴포넌트

퍼블코드(퍼블로그의 코드 관리 서비스) 페이지에서만 사용하는 컴포넌트입니다.
기본 브랜드 가이드(`components.md`)의 색상·폰트·레이아웃을 기반으로 합니다.

---

## SubTab 버튼

퍼블코드 내 탭 전환 UI. 알약형(border-radius 9999px) · height 44px.

| 상태 | 클래스 | 배경 | 텍스트 |
|------|--------|------|--------|
| 활성 | `.subtab-active` | `var(--trendy)` | `#fff` |
| 비활성 | `.subtab-inactive` | `#fff` | `var(--text-muted)` |
| 퍼플 강조 | `.subtab-purple` | `#ECEEFF` | `#515382` |

```css
.subtab-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  height: 44px;
  padding: 0 16px;
  border-radius: 9999px;
  font-size: 13px;
  font-weight: 600;
  border: 1.5px solid;
  cursor: pointer;
  transition: all 0.15s;
}

.subtab-active   { background: var(--trendy); color: #fff; border-color: var(--trendy); }
.subtab-inactive { background: #fff; color: var(--text-muted); border-color: rgba(0,0,0,0.08); }
.subtab-purple   { background: #ECEEFF; color: #515382; border-color: rgba(81,83,130,0.3); }

/* 카운트 숫자 */
.subtab-count { font-size: 11px; font-weight: 700; opacity: 0.7; }
```

```html
<!-- 퍼블코드 활성 상태 -->
<div style="display: flex; gap: 8px;">
  <button class="subtab-btn subtab-active">퍼블코드 <span class="subtab-count">5</span></button>
  <button class="subtab-btn subtab-inactive">그룹코드 <span class="subtab-count">3</span></button>
</div>
<!-- 그룹코드 선택 시 -->
<div style="display: flex; gap: 8px;">
  <button class="subtab-btn subtab-inactive">퍼블코드</button>
  <button class="subtab-btn subtab-purple">그룹코드 <span class="subtab-count">3</span></button>
</div>
```

---

## CodeChip (코드 표시 칩)

퍼블코드·그룹코드를 표시하는 인라인 칩 컴포넌트.

| 종류 | 클래스 | 배경 | 텍스트 |
|------|--------|------|--------|
| 퍼블코드 | `.codechip-pub` | `#EEF0F8` | `var(--trendy)` |
| 그룹코드 | `.codechip-grp` | `#ECEEFF` | `#515382` |

```css
.codechip {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  height: 36px;
  padding: 0 8px 0 12px;
  border-radius: 8px;
  font-family: 'Montserrat', monospace;
  font-weight: 700;
  font-size: 14px;
  letter-spacing: 0.08em;
}

.codechip-pub { background: #EEF0F8; color: var(--trendy); }
.codechip-grp { background: #ECEEFF; color: #515382; }

/* 복사 버튼 (칩 오른쪽 끝) */
.codechip-copy {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 24px;
  min-width: 32px;
  padding: 0 8px;
  border-radius: 6px;
  font-size: 11px;
  font-weight: 600;
  color: #fff;
  border: none;
  cursor: pointer;
}

.codechip-pub .codechip-copy { background: var(--trendy); }
.codechip-grp .codechip-copy { background: #515382; }
```

```html
<div class="codechip codechip-pub">PUBL-7K3M-A2<span class="codechip-copy">복사</span></div>
<div class="codechip codechip-grp">GRP-2024-XZ7<span class="codechip-copy">복사</span></div>
```

---

## D-day 배지

코드 만료일까지 남은 일수를 표시하는 상태 배지. 3단계 긴급도로 색상 분기.

| 상태 | 클래스 | 배경 | 텍스트 |
|------|--------|------|--------|
| 여유 (D-8+) | `.dday-safe` | `var(--belief)` #F0F1F6 | `var(--text-muted)` #777 |
| 주의 (D-3~7) | `.dday-warn` | `#FFF3CD` | `#856404` |
| 긴급 (D-0~2) | `.dday-urgent` | `#FFE5E5` | `#DC3545` |

```css
.dday-badge {
  display: inline-flex;
  align-items: center;
  height: 20px;
  padding: 0 8px;
  border-radius: 4px;
  font-size: 10px;
  font-weight: 700;
  white-space: nowrap;
}

.dday-safe   { background: var(--belief); color: var(--text-muted); }
.dday-warn   { background: #FFF3CD; color: #856404; }
.dday-urgent { background: #FFE5E5; color: #DC3545; }
```

```html
<span class="dday-badge dday-safe">D-15</span>
<span class="dday-badge dday-warn">D-5</span>
<span class="dday-badge dday-urgent">D-1</span>
```

---

## PublCard (퍼블카드 v2)

퍼블코드를 시각적으로 표시하는 카드 컴포넌트. border-radius 28px.

```css
.publcard-wrap {
  border-radius: 28px;
  background: #fff;
  border: 1px solid rgba(0,0,0,0.06);
  overflow: hidden;
  width: 420px;
  max-width: 100%;
  box-shadow: 0 20px 50px -20px rgba(0,0,0,0.2);
}

/* 썸네일 영역 */
.publcard-thumb {
  aspect-ratio: 4/3;
  background: #1A2B5F;
  position: relative;
  display: flex;
  align-items: flex-end;
  padding: 16px;
  overflow: hidden;
}

/* 배경 장식 원 */
.publcard-thumb-circle {
  position: absolute;
  right: -20px;
  bottom: -20px;
  width: 110px;
  height: 110px;
  border-radius: 50%;
  background: var(--friendly);
  opacity: 0.85;
}

/* 상태 배지 (좌상단) */
.publcard-status {
  position: absolute;
  top: 14px;
  left: 14px;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  height: 28px;
  padding: 0 10px;
  border-radius: 9999px;
  background: rgba(255,255,255,0.95);
  font-size: 11px;
  font-weight: 700;
  color: var(--stability);
}

.publcard-status-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--friendly);
}

/* 미인증 배지 (우상단) */
.publcard-noauth {
  position: absolute;
  top: 14px;
  right: 14px;
  display: inline-flex;
  align-items: center;
  height: 28px;
  padding: 0 10px;
  border-radius: 9999px;
  background: var(--friendly);
  font-size: 10.5px;
  font-weight: 800;
  color: var(--stability);
}

/* 바디 */
.publcard-body { padding: 20px 24px 8px; }

.publcard-price-label {
  font-size: 10.5px;
  font-weight: 700;
  letter-spacing: 0.18em;
  color: var(--text-muted);
}

.publcard-price {
  font-family: 'Montserrat', sans-serif;
  font-size: 26px;
  font-weight: 800;
  letter-spacing: -0.03em;
  color: var(--stability);
  margin-top: 2px;
}

.publcard-price small { font-size: 14px; font-weight: 700; margin-left: 2px; }

/* 푸터 */
.publcard-footer { padding: 0 24px 20px; }

.publcard-code-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 11px;
  color: var(--text-muted);
  font-weight: 500;
  margin-bottom: 12px;
}

.publcard-code-val {
  font-family: 'Montserrat', sans-serif;
  font-size: 15px;
  font-weight: 800;
  letter-spacing: 0.06em;
  color: var(--stability);
}

/* 액션 버튼 */
.publcard-actions { display: flex; gap: 8px; }

.publcard-btn-url {
  flex: 1;
  height: 44px;
  border-radius: 9999px;
  border: 1.5px solid rgba(0,0,0,0.12);
  background: #fff;
  font-size: 12.5px;
  font-weight: 700;
  cursor: pointer;
}

.publcard-btn-share {
  flex: 1;
  height: 44px;
  border-radius: 9999px;
  background: var(--trendy);
  color: #fff;
  font-size: 12.5px;
  font-weight: 700;
  border: none;
  cursor: pointer;
}
```

```html
<div class="publcard-wrap">
  <div class="publcard-thumb">
    <div class="publcard-thumb-circle"></div>
    <span class="publcard-status">
      <span class="publcard-status-dot"></span>퍼블코드 · 활성
    </span>
    <span class="publcard-noauth">가입 없이 구매 ✓</span>
    <div style="margin-top: auto;">
      <p style="font-size: 11px; color: rgba(255,255,255,0.6);">PRODUCT NAME</p>
      <p style="font-size: 16px; font-weight: 700; color: #fff;">상품 제목</p>
    </div>
  </div>
  <div class="publcard-body">
    <div>
      <p class="publcard-price-label">PRICE</p>
      <p class="publcard-price">37,800<small>원</small></p>
    </div>
  </div>
  <div class="publcard-footer">
    <div class="publcard-code-row">
      <span>CODE</span>
      <span class="publcard-code-val">PUBL-7K3M-A2</span>
    </div>
    <div class="publcard-actions">
      <button class="publcard-btn-url">🔗 URL 복사</button>
      <button class="publcard-btn-share">▷ 코드 공유</button>
    </div>
  </div>
</div>
```

---

## Step Indicator (진행 상태 표시줄)

다단계 폼 상단에 표시되는 진행 상태 바. Navy(퍼블코드 만들기)와 Purple(그룹코드 만들기) 2가지 테마.

| 요소 | 스타일 |
|------|--------|
| STEP N/N 텍스트 | Montserrat 700 · 11px · letter-spacing 0.12em · `var(--text-muted)` · 현재 스텝 강조색 |
| 프로그레스 바 트랙 | height 3px · border-radius 9999px · `rgba(0,0,0,0.06)` |
| 프로그레스 바 채움 (Navy) | `#222450` · transition 300ms |
| 프로그레스 바 채움 (Purple/완료) | `#7b42f6` · transition 300ms |
| 스텝 이름 | 13px 600 · 강조색 |

```css
.step-indicator { display: flex; align-items: center; gap: 10px; }

.step-num {
  font-family: 'Montserrat', sans-serif;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  color: var(--text-muted);
  white-space: nowrap;
}

.step-num .step-accent { color: var(--trendy); }
.step-num .step-accent.purple { color: #7b42f6; }

.step-track {
  flex: 1;
  height: 3px;
  border-radius: 9999px;
  background: rgba(0,0,0,0.06);
  overflow: hidden;
}

.step-fill { height: 100%; border-radius: 9999px; transition: width 300ms; background: var(--trendy); }
.step-fill.purple { background: #7b42f6; }

.step-label { font-size: 13px; font-weight: 600; white-space: nowrap; color: var(--trendy); }
.step-label.purple { color: #7b42f6; }
```

```html
<!-- Navy 테마 (퍼블코드 만들기) — STEP 1/3 -->
<div class="step-indicator">
  <span class="step-num">STEP <span class="step-accent">1</span> / 3</span>
  <div class="step-track"><div class="step-fill" style="width: 33%"></div></div>
  <span class="step-label">상품 선택</span>
</div>

<!-- Purple 테마 (그룹코드 만들기) — STEP 3/3 완료 -->
<div class="step-indicator">
  <span class="step-num">STEP <span class="step-accent purple">3</span> / 3</span>
  <div class="step-track"><div class="step-fill purple" style="width: 100%"></div></div>
  <span class="step-label purple">완료</span>
</div>
```

---

## Stepper (수량 조절)

숫자 입력 전용 증감 버튼 UI.

| 항목 | 스펙 |
|------|------|
| 버튼 크기 | 36 × 36px · border-radius 9999px |
| 버튼 테두리 | `border: 1.5px solid rgba(0,0,0,0.12)` |
| 수치 | Montserrat 700 · min-width 40px · text-align center · 14px |

```css
.stepper { display: inline-flex; align-items: center; border: 1.5px solid rgba(0,0,0,0.12); border-radius: 9999px; overflow: hidden; }

.stepper-btn {
  width: 36px;
  height: 36px;
  border: none;
  background: #fff;
  cursor: pointer;
  font-size: 18px;
  font-weight: 300;
  color: var(--stability);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background 0.15s;
}

.stepper-btn:hover { background: var(--belief); }

.stepper-val {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  min-width: 40px;
  text-align: center;
  font-size: 14px;
  color: var(--stability);
}
```

```html
<div class="stepper">
  <button class="stepper-btn">−</button>
  <span class="stepper-val">1</span>
  <button class="stepper-btn">+</button>
</div>
```

---

## Field & InlineHelp (퍼블코드 폼)

퍼블코드 내 입력 폼. 기본 Field(border-radius 4px)와 달리 **8px** 적용.

```css
.field-group { margin-bottom: 20px; }

.field-label {
  display: block;
  font-size: 13px;
  font-weight: 600;
  color: var(--stability);
  margin-bottom: 8px;
}

.field-input-lg {
  width: 100%;
  height: 48px;
  border: 1px solid var(--border);
  border-radius: 8px;   /* 퍼블코드 폼은 8px */
  padding: 0 14px;
  font-size: 14px;
  font-family: 'Noto Sans KR', sans-serif;
  color: var(--stability);
  background: #fff;
  outline: none;
}

.field-input-lg:focus { border-color: var(--trendy); }

.field-hint {
  font-size: 11.5px;
  color: var(--text-muted);
  margin-top: 6px;
}

/* 인라인 도움말 버튼 */
.inlinehelp-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  height: 36px;
  padding: 0 12px;
  border-radius: 9999px;
  background: #fff;
  border: 1px solid rgba(0,0,0,0.15);
  font-size: 12px;
  font-weight: 500;
  cursor: pointer;
}

.inlinehelp-icon {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: rgba(0,0,0,0.1);
  font-size: 10px;
  font-weight: 700;
  color: var(--text-muted);
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
```

```html
<!-- Field -->
<div class="field-group">
  <label class="field-label">코드 제목</label>
  <input class="field-input-lg" type="text" placeholder="예: 아이돌 굿즈 포토카드 세트">
  <p class="field-hint">💡 받는 사람에게 표시되는 이름이에요</p>
</div>

<!-- InlineHelp -->
<button class="inlinehelp-btn">
  <span class="inlinehelp-icon">?</span> 퍼블코드란?
</button>
```

---

## Stat Card (퍼블코드 버전)

기본 Stat Card(components.md)보다 더 큰 수치와 다른 레이아웃.

```css
.stat-card-pc {
  border-radius: 16px;
  padding: 20px;
  border: 1px solid rgba(0,0,0,0.06);
  background: #fff;
}

/* 경고 상태 */
.stat-card-pc.stat-warn {
  background: #fff7ed;
  border-color: rgba(234,88,12,0.25);
}

.stat-card-pc .stat-label { font-size: 13px; font-weight: 500; color: var(--text-muted); }
.stat-card-pc .stat-value {
  font-family: 'Montserrat', sans-serif;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: -0.03em;
  color: var(--stability);
  margin-top: 4px;
}
.stat-card-pc .stat-sub { font-size: 12px; color: var(--text-muted); margin-top: 4px; }

.stat-card-pc.stat-warn .stat-label,
.stat-card-pc.stat-warn .stat-value { color: #ea580c; }
```

```html
<div class="stat-card-pc">
  <p class="stat-label">공유한 코드</p>
  <p class="stat-value">8</p>
  <p class="stat-sub">퍼블 5 · 그룹 3</p>
</div>
<!-- 경고 상태 -->
<div class="stat-card-pc stat-warn">
  <p class="stat-label">⚠️ 마감 임박</p>
  <p class="stat-value">2</p>
  <p class="stat-sub">D-3 이하 코드</p>
</div>
```

---

## 체크박스 (대량 선택 UX)

퍼블코드 대량 선택 목록에 사용. SVG 방식으로 외부 이미지 의존성 없음.

```css
.cb-wrap {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
}

.cb-input { display: none; }

.cb-box {
  width: 18px;
  height: 18px;
  border-radius: 4px;
  flex-shrink: 0;
  display: grid;
  place-items: center;
}

.cb-input:not(:checked) + .cb-box {
  background-image: url('https://www.bizfactory.co.kr/include/img/login/checkbox.png');
  background-size: 100% 100%;
  background-repeat: no-repeat;
  border: 1.5px solid #d1d5db;
  background-color: #fff;
}

.cb-input:checked + .cb-box {
  background-color: #222450;
  background-image: url('https://www.bizfactory.co.kr/include/img/login/checkbox_on.png');
  background-size: 100% 100%;
  background-repeat: no-repeat;
  border: none;
}

.cb-label { font-size: 13px; color: var(--text-body); }
```

```html
<label class="cb-wrap">
  <input class="cb-input" type="checkbox">
  <span class="cb-box"></span>
  <span class="cb-label">항목 이름</span>
</label>
```

---

## 코드 등록 카드 (reg-card)

코드 번호를 직접 입력해 퍼블코드/그룹코드를 등록하는 UI.
코드 입력창에 `JetBrains Mono` 폰트 사용. `<head>`에 아래 임포트 추가 필요:

```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
```

```css
.reg-card {
  background: #fff;
  border-radius: 24px;
  border: 1px solid rgba(0,0,0,0.06);
  padding: 32px 28px;
  max-width: 400px;
}

.reg-icon {
  width: 64px;
  height: 64px;
  border-radius: 50%;
  background: var(--belief);
  display: flex;
  align-items: center;
  justify-content: center;
}

.reg-input {
  width: 100%;
  height: 64px;
  border-radius: 16px;
  border: 2px solid rgba(0,0,0,0.10);
  font-family: 'JetBrains Mono', monospace;
  font-size: 24px;
  font-weight: 700;
  letter-spacing: 0.18em;
  text-align: center;
  outline: none;
}

.reg-input:focus { border-color: var(--trendy); }

/* 자동판별 배지 */
.reg-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  height: 28px;
  padding: 0 12px;
  border-radius: 9999px;
  font-size: 12px;
  font-weight: 700;
}

.reg-badge.pub { background: #EEF0F8; color: var(--trendy); }
.reg-badge.grp { background: var(--group-purple-soft); color: var(--attention); }

.reg-badge-dot { width: 6px; height: 6px; border-radius: 50%; }
.reg-badge.pub .reg-badge-dot { background: var(--trendy); }
.reg-badge.grp .reg-badge-dot { background: var(--attention); }

/* CTA 버튼 */
.reg-btn {
  width: 100%;
  height: 56px;
  border-radius: 16px;
  border: none;
  font-size: 15px;
  font-weight: 700;
  color: #fff;
  cursor: pointer;
}

.reg-btn.pub      { background: var(--trendy); }
.reg-btn.grp      { background: var(--attention); }
.reg-btn.disabled { opacity: 0.4; cursor: not-allowed; }
```

```html
<div class="reg-card">
  <div class="reg-icon"><!-- 아이콘 SVG --></div>
  <!-- ① 미입력 상태 -->
  <input class="reg-input" placeholder="코드 입력">
  <button class="reg-btn disabled">코드 확인하기</button>
  <!-- ② 퍼블코드 인식 시 -->
  <input class="reg-input" value="0RVTZDRDP6">
  <span class="reg-badge pub"><span class="reg-badge-dot"></span>퍼블코드로 인식됨</span>
  <button class="reg-btn pub">코드 확인하기</button>
  <!-- ③ 그룹코드 인식 시 -->
  <input class="reg-input" value="GRP2024A">
  <span class="reg-badge grp"><span class="reg-badge-dot"></span>그룹코드로 인식됨</span>
  <button class="reg-btn grp">그룹 상품 확인하기 →</button>
</div>
```

---

## 대량 선택 UX (bulk-item)

퍼블코드 대량 선택 목록 아이템. 선택 시 border + 배경색 변경.

```css
.bulk-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 12px;
}

.bulk-count-badge {
  height: 28px;
  padding: 0 12px;
  border-radius: 9999px;
  background: var(--group-purple-soft);
  color: var(--attention);
  font-size: 12px;
  font-weight: 700;
  display: inline-flex;
  align-items: center;
}

/* 필터 탭 */
.bulk-filter-tab {
  height: 28px;
  padding: 0 12px;
  border-radius: 9999px;
  font-size: 11px;
  font-weight: 600;
  border: 1.5px solid transparent;
  cursor: pointer;
}

.bulk-filter-tab.on  { background: var(--trendy); color: #fff; border-color: var(--trendy); }
.bulk-filter-tab.off { background: #f3f4f6; color: #4b5563; }

/* 아이템 */
.bulk-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  border-radius: 16px;
  border: 1.5px solid rgba(0,0,0,0.08);
  margin-bottom: 8px;
  transition: all 0.15s;
}

.bulk-item.on { border-color: var(--trendy); background: var(--group-purple-soft); }

.bulk-emoji {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: var(--belief);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  flex-shrink: 0;
}

.bulk-title { font-size: 14px; font-weight: 600; }
.bulk-spec  { font-size: 11px; color: var(--text-muted); margin-top: 2px; }
.bulk-price { font-size: 15px; font-weight: 800; margin-left: auto; }
```

```html
<div class="bulk-header">
  <div>
    <p>묶을 퍼블코드 선택</p>
    <p>2개 이상 선택해야 그룹을 만들 수 있어요.</p>
  </div>
  <span class="bulk-count-badge">2개 선택</span>
</div>
<div style="display: flex; gap: 6px;">
  <button class="bulk-filter-tab on">전체</button>
  <button class="bulk-filter-tab off">공개</button>
  <button class="bulk-filter-tab off">비공개</button>
</div>
<!-- 선택된 아이템 -->
<div class="bulk-item on">
  <div class="bulk-emoji">🔑</div>
  <div style="flex: 1;">
    <p class="bulk-title">봄 아크릴 키링</p>
    <p class="bulk-spec">아크릴·양면·30×30mm</p>
  </div>
  <span class="bulk-price">12,000원</span>
</div>
<!-- 미선택 아이템 -->
<div class="bulk-item">
  <div class="bulk-emoji">🏅</div>
  <div style="flex: 1;">
    <p class="bulk-title">원형 뱃지 세트</p>
    <p class="bulk-spec">44mm 원형·3개입</p>
  </div>
  <span class="bulk-price">7,200원</span>
</div>
```

---

## 그룹코드 종료 상태 카드 (grp-card)

그룹 내 일부·전체 코드가 종료됐을 때 상태를 표시하는 카드.

```css
.grp-card {
  background: #fff;
  border-radius: 24px;
  border: 1px solid rgba(0,0,0,0.06);
  overflow: hidden;
}

/* 상태 스트립 */
.grp-strip {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 12px 20px;
  background: var(--group-purple-soft);
}

.grp-strip-dot   { width: 6px; height: 6px; border-radius: 50%; background: var(--attention); }
.grp-strip-label { font-size: 12px; font-weight: 700; color: var(--attention); }

/* 종료 상태 텍스트 */
.grp-strip-partial { font-size: 11px; font-weight: 600; color: #c2410c; } /* 일부 종료 */
.grp-strip-all     { font-size: 11px; font-weight: 600; color: #dc2626; } /* 전체 종료 */

/* 타일 행 */
.grp-items-row {
  display: flex;
  gap: 8px;
  padding: 16px 20px;
  overflow-x: auto;
  scrollbar-width: none;
}

.grp-tile {
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 64px;
  gap: 6px;
}

.grp-thumb {
  width: 56px;
  height: 56px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  position: relative;
}

.grp-thumb.active-t  { background: var(--belief); }
.grp-thumb.soldout-t { background: rgba(0,0,0,0.08); opacity: 0.6; }

/* SOLD OUT 오버레이 */
.grp-so-overlay {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.52);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.grp-so-text { color: #fff; font-weight: 900; font-size: 7px; text-align: center; }

.grp-tile-name { font-size: 10px; font-weight: 600; text-align: center; line-height: 1.3; }
```

```html
<div class="grp-card">
  <div class="grp-strip">
    <div class="grp-strip-dot"></div>
    <span class="grp-strip-label">그룹 공유</span>
    <!-- 일부 종료 시 추가 -->
    <span class="grp-strip-partial">· 일부 종료</span>
  </div>
  <div class="grp-items-row">
    <!-- 정상 아이템 -->
    <div class="grp-tile">
      <div class="grp-thumb active-t">🌸</div>
      <p class="grp-tile-name">스티커팩</p>
    </div>
    <!-- SOLD OUT 아이템 -->
    <div class="grp-tile">
      <div class="grp-thumb soldout-t">
        <span>🌿</span>
        <div class="grp-so-overlay">
          <span class="grp-so-text">SOLD<br>OUT</span>
        </div>
      </div>
      <p class="grp-tile-name">엽서 B</p>
    </div>
  </div>
</div>
```

---

## 그룹관리 탭 & 통계 (grp-tab / grp-stat)

그룹 코드가 10개 이상일 때의 탭 스크롤 + 통계 카드 레이아웃.

```css
/* 수평 스크롤 탭 바 */
.grp-tab-bar {
  display: flex;
  gap: 4px;
  overflow-x: auto;
  scrollbar-width: none;
  padding-bottom: 4px;
}

.grp-tab-pill {
  flex-shrink: 0;
  height: 36px;
  padding: 0 14px;
  border-radius: 9999px;
  font-size: 12px;
  font-weight: 700;
  white-space: nowrap;
  border: none;
  cursor: pointer;
}

.grp-tab-pill.act   { background: var(--trendy); color: #fff; }
.grp-tab-pill.inact { background: var(--belief); color: var(--text-body); }

/* 통계 카드 그리드 */
.grp-stat-row {
  display: flex;
  gap: 12px;
  margin-top: 16px;
  flex-wrap: wrap;
}

.grp-stat {
  flex: 1;
  min-width: 80px;
  background: var(--belief);
  border-radius: 12px;
  padding: 14px 16px;
}

/* D-day 강조 통계 */
.grp-stat.dday { background: #eef2ff; }
.grp-stat.dday .grp-stat-val { color: var(--attention); }

.grp-stat-val   { font-family: 'Montserrat', sans-serif; font-size: 22px; font-weight: 800; color: var(--trendy); }
.grp-stat-label { font-size: 10.5px; color: var(--text-muted); margin-top: 2px; }
```

```html
<div class="grp-tab-bar">
  <button class="grp-tab-pill act">GRP-A · 봄 세트</button>
  <button class="grp-tab-pill inact">GRP-B · 여름</button>
  <button class="grp-tab-pill inact">GRP-C · 가을</button>
</div>
<div class="grp-stat-row">
  <div class="grp-stat">
    <p class="grp-stat-val">3</p>
    <p class="grp-stat-label">포함 코드</p>
  </div>
  <div class="grp-stat">
    <p class="grp-stat-val">18</p>
    <p class="grp-stat-label">공유 횟수</p>
  </div>
  <!-- D-day 강조 통계 -->
  <div class="grp-stat dday">
    <p class="grp-stat-val">D-14</p>
    <p class="grp-stat-label">만료까지</p>
  </div>
</div>
```

---

## 마이코드 목록 (mycode)

내 코드 / 받은 코드를 탭으로 구분하는 목록 UI.

```css
/* 메인 탭 */
.mycode-main-tabs {
  display: flex;
  border-bottom: 2px solid var(--border);
  margin-bottom: 20px;
}

.mycode-main-tab {
  padding: 10px 20px;
  font-size: 14px;
  font-weight: 600;
  border-bottom: 3px solid transparent;
  margin-bottom: -2px;
  cursor: pointer;
  background: none;
  border-top: none;
  border-left: none;
  border-right: none;
}

.mycode-main-tab.on  { color: var(--trendy); border-bottom-color: var(--trendy); }
.mycode-main-tab.off { color: var(--text-muted); }

/* 섹션 구분 라벨 */
.mycode-section-label {
  font-size: 10.5px;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
  color: var(--text-muted);
  margin: 16px 0 8px;
}

/* 코드 카드 */
.mycode-card {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  border-radius: 16px;
  border: 1px solid var(--border);
  background: #fff;
  margin-bottom: 8px;
}

.mycode-card.ended { opacity: 0.7; }

.mycode-thumb {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: var(--belief);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 22px;
  flex-shrink: 0;
}

.mycode-card.ended .mycode-thumb { opacity: 0.5; }

.mycode-title { font-size: 14px; font-weight: 600; }
.mycode-meta  { font-size: 11px; color: var(--text-muted); margin-top: 2px; }

/* 상태 배지 */
.mycode-status {
  height: 20px;
  padding: 0 8px;
  border-radius: 4px;
  font-size: 10px;
  font-weight: 700;
  display: inline-flex;
  align-items: center;
  white-space: nowrap;
}

.mycode-status.active-s  { background: #dcfce7; color: #15803d; }
.mycode-status.ended-s   { background: #f3f4f6; color: #6b7280; }
.mycode-status.soldout-s { background: #fef2f2; color: #dc2626; }

.mycode-price { font-family: 'Montserrat', sans-serif; font-size: 14px; font-weight: 800; margin-left: auto; }
```

```html
<div class="mycode-main-tabs">
  <button class="mycode-main-tab on">내 코드</button>
  <button class="mycode-main-tab off">받은 코드</button>
</div>
<p class="mycode-section-label">활성 · 8개</p>
<!-- 활성 코드 카드 -->
<div class="mycode-card">
  <div class="mycode-thumb">🔑</div>
  <div style="flex: 1;">
    <p class="mycode-title">봄 아크릴 키링</p>
    <p class="mycode-meta">D-23 · 조회 18 · 구매 7</p>
  </div>
  <span class="mycode-status active-s">활성</span>
  <span class="mycode-price">12,000원</span>
</div>
<p class="mycode-section-label">종료 · 4개</p>
<!-- 종료 코드 카드 -->
<div class="mycode-card" style="opacity: .7;">
  <div class="mycode-thumb" style="opacity: .5;">🧣</div>
  <div style="flex: 1;">
    <p class="mycode-title">패브릭 포스터 소형</p>
    <p class="mycode-meta">2026.03.31 종료 · 구매 14</p>
  </div>
  <span class="mycode-status ended-s">종료</span>
  <span class="mycode-price" style="color: var(--text-muted);">18,000원</span>
</div>
<!-- 품절 코드 카드 -->
<div class="mycode-card" style="opacity: .7;">
  <div class="mycode-thumb" style="opacity: .5;">🎴</div>
  <div style="flex: 1;">
    <p class="mycode-title">한정판 포카 12종</p>
    <p class="mycode-meta">2026.04.25 품절 · 구매 88</p>
  </div>
  <span class="mycode-status soldout-s">품절</span>
  <span class="mycode-price" style="color: var(--text-muted);">22,000원</span>
</div>
```

---

## PubSubLink (상단 탭 바)

퍼블코드 프로토타입 상단 네이비 탭 바. 선택 상태에 따라 3가지 스타일로 분기.

| 탭 유형 | 해당 화면 | 선택 시 스타일 |
|--------|----------|--------------|
| Navy | 마이 코드 · 그룹관리 · 마이코드 10+ | `background: var(--trendy)` · `border: 2px solid #fff` · `color: #fff` |
| Purple | 그룹코드 만들기 · 대량 선택 · 그룹코드 종료 | `background: var(--attention)` · `color: #fff` |
| Default | 퍼블코드 만들기 · 코드 등록 등 | `background: #fff` · `color: var(--trendy)` |
| 비선택 (공통) | 모든 탭 | `color: rgba(255,255,255,0.75)` · hover `bg: rgba(255,255,255,0.1)` |

```css
.pubsublink-bar {
  display: flex;
  gap: 6px;
  background: var(--trendy);
  padding: 8px 12px;
  overflow-x: auto;
  scrollbar-width: none;
}

.pubsublink-btn {
  flex-shrink: 0;
  height: 28px;
  padding: 0 12px;
  border-radius: 9999px;
  font-size: 12.5px;
  font-weight: 600;
  border: none;
  cursor: pointer;
  color: rgba(255,255,255,0.75);
  background: transparent;
  transition: all 0.15s;
  white-space: nowrap;
}

.pubsublink-btn:hover { background: rgba(255,255,255,0.1); }

.pubsublink-btn.type-navy    { background: var(--trendy); border: 2px solid #fff; color: #fff; }
.pubsublink-btn.type-purple  { background: var(--attention); color: #fff; }
.pubsublink-btn.type-default { background: #fff; color: var(--trendy); }
```

```html
<div class="pubsublink-bar">
  <button class="pubsublink-btn type-navy">마이 코드</button>
  <button class="pubsublink-btn type-purple">그룹코드 만들기</button>
  <button class="pubsublink-btn type-default">퍼블코드 만들기</button>
  <button class="pubsublink-btn">코드 등록</button>
</div>
```

---

## MyPublog LNB

마이퍼블로그 사이드바 네비게이션. 너비 220px · PC 전용.

```css
.lnb-wrap { width: 220px; background: #fff; flex-shrink: 0; }

.lnb-header { background: var(--trendy); padding: 16px 20px; color: #fff; }

.lnb-section-label {
  font-size: 9.5px;
  font-weight: 700;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #777;
  padding: 12px 20px 4px;
}

.lnb-item {
  display: block;
  font-size: 12.5px;
  padding: 7px 20px;
  color: var(--text-body);
  cursor: pointer;
  text-decoration: none;
}

.lnb-item:hover     { background: var(--belief); }
.lnb-item.active    { color: var(--trendy); font-weight: 600; background: rgba(34,36,80,0.04); }
.lnb-item.highlight { color: var(--attention); font-weight: 600; }
```

```html
<nav class="lnb-wrap">
  <div class="lnb-header">
    <p style="font-family: 'Montserrat', sans-serif; font-size: 13px; font-weight: 700;">MY PUBLOG</p>
  </div>
  <p class="lnb-section-label">코드 관리</p>
  <a class="lnb-item active">마이 코드</a>
  <a class="lnb-item highlight">그룹관리</a>
  <a class="lnb-item">코드 등록</a>
  <p class="lnb-section-label">계정</p>
  <a class="lnb-item">주문 내역</a>
  <a class="lnb-item">설정</a>
</nav>
```

---

## CSS 변수 추가 필요

퍼블코드 컴포넌트에서 사용하는 추가 변수. 보일러플레이트 `:root`에 추가하세요:

```css
--group-purple-soft: #ECEEFF;  /* 그룹코드 배지·배경 */
```

---

## 사용 시 주의

- 퍼블코드 컴포넌트는 **기본 CSS 변수(`:root`)가 선언된 상태에서만** 동작합니다.
- `layout.md`의 HTML 보일러플레이트를 베이스로 사용하세요.
- 퍼블코드 페이지에서는 기본 컴포넌트(`components.md`)와 이 파일을 함께 참조합니다.
