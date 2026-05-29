# 아이콘 가이드

서비스 전반에 사용되는 아이콘 규정 및 라이브러리

---

## 아이콘 컬러 3종

| 이름 | HEX | 사용처 |
|------|-----|--------|
| KEY · TRENDY | `#222450` | 기본 아이콘 컬러. 흰색·라이트 배경 위 모든 UI 아이콘. 가장 지배적으로 활용 |
| BLACK | `#000000` | 모노톤·고대비가 필요한 인쇄물·제휴 채널·블랙 베이스 페이지 |
| WHITE · CLEAR | `#FFFFFF` | 어두운 배경(키컬러·블랙·이미지) 위 역상 버전. 헤더·이미지 오버레이 |

---

## DO / DON'T

**DO**
- 흰색·라이트 배경 위 UI에서는 항상 `#222450`(Trendy)을 우선 적용
- 키컬러·블랙·이미지 등 어두운 배경에서는 반드시 화이트(`#fff`) 역상 버전 사용
- 한 화면 안에서는 같은 스타일(Linear 또는 Bold) 한 가지만 사용

**DON'T**
- 옐로우·레드·스카이블루 등 다른 브랜드 색을 아이콘 자체에 적용 금지
- 가로세로 비율 왜곡, 의미가 명확한 아이콘의 임의 회전·반전 금지 (화살표 제외)
- 이미지·사진 위에 아이콘 직접 배치 금지 — 반투명 오버레이·뱃지 박스로 감싸 사용

---

## 크기 규격

| 크기 | 사용처 |
|------|--------|
| 16px | 인라인 텍스트, 캡션 |
| 20px | 버튼, 폼 입력 |
| **24px** (기본) | GNB, 헤더 아이콘 바 |
| 32px | 퀵메뉴, 카드 라벨 |

**최소 여백 (Safe Area):** 아이콘 외곽 상하좌우 아이콘 크기의 25% 이상
- 24px 아이콘 → 최소 6px 여백
- 32px 아이콘 → 최소 8px 여백

---

## 아이콘 라이브러리 (총 81개)

스타일: Linear / Bold 2가지 (SVG 기반) + PNG 기반 1개

### Commerce · 쇼핑·상거래 (12)

| 영문명 | 한글명 |
|--------|--------|
| bag | 장바구니 |
| bag-2 | 장바구니 2 |
| bag-happy | 쇼핑 즐기기 |
| shopping-cart | 카트 |
| shopping-bag | 쇼핑백 |
| shop | 스토어 |
| gift | 선물·기프트 |
| ticket-discount | 쿠폰·할인 |
| tag | 태그 |
| tag-2 | 태그 2 |
| box | 박스·포장 |
| truck-tick | 배송·운송 |

### User · 사용자·계정 (9)

| 영문명 | 한글명 |
|--------|--------|
| user | 사용자 |
| profile-circle | 프로필 |
| profile-2user | 다중 사용자 |
| people | 그룹 |
| login | 로그인 |
| logout | 로그아웃 |
| lock | 잠금 |
| unlock | 잠금 해제 |
| global | 언어 |

### Action · 액션 (19)

| 영문명 | 한글명 |
|--------|--------|
| heart | 찜·좋아요 |
| heart-add | 찜 추가 |
| like-1 | 좋아요 |
| share | 공유 |
| search-normal-1 | 검색 |
| edit | 수정 |
| add | 추가 |
| close-circle | 닫기 |
| filter | 필터 |
| sort | 정렬 |
| send | 전송 |
| trash | 삭제 |
| refresh | 새로고침 |
| repeat | 반복 |
| eye | 공개 |
| eye-slash | 비공개 |
| hashtag | 해시태그 |
| copy | 복사 |
| download | 다운로드 |

### Payment · 결제·금융 (5)

| 영문명 | 한글명 |
|--------|--------|
| card | 카드 |
| wallet | 지갑 |
| dollar-circle | 금액 |
| coin | 코인·포인트 |
| money | 머니 |

### Design · 디자인·미디어 (10)

| 영문명 | 한글명 |
|--------|--------|
| image | 이미지 |
| gallery | 갤러리 |
| camera | 카메라 |
| video | 영상 |
| paintbucket | 페인트 |
| brush | 브러시 |
| color-swatch | 컬러 스와치 |
| 3dcube | 3D 큐브 |
| scissor | 가위·컷팅 |
| printer | 프린터 |

### Communication · 알림·소통 (4)

| 영문명 | 한글명 |
|--------|--------|
| notification | 알림 |
| message | 메시지 |
| sms | SMS |
| star | 별점 |

### Navigation · 네비게이션 (8)

| 영문명 | 한글명 |
|--------|--------|
| home-2 | 홈 |
| category | 카테고리 |
| menu | 메뉴 |
| menu-board | 메뉴 보드 |
| arrow-left | 왼쪽 |
| arrow-right | 오른쪽 |
| arrow-up | 위쪽 |
| arrow-down | 아래쪽 |

### Place · 시간·위치 (5)

| 영문명 | 한글명 |
|--------|--------|
| location | 위치 |
| map | 지도 |
| calendar | 캘린더 |
| clock | 시계 |
| timer | 타이머 |

### System · 시스템·인증 (7)

| 영문명 | 한글명 |
|--------|--------|
| setting-2 | 설정 |
| award | 어워드 |
| medal-star | 메달 |
| verify | 인증 |
| shield-tick | 보안 |
| tick-circle | 체크 |
| close-square | 닫기 사각 |

### Publog Code · 퍼블코드 (1)

> SVG 아이콘이 아닌 PNG 이미지 기반. Linear/Bold 스타일 전환 없이 항상 동일 이미지 노출.

| 영문명 | 한글명 | 형식 | 이미지 URL |
|--------|--------|------|------------|
| share-publog | 공유 | PNG | 기본/블랙: `https://www.publog.co.kr/sub_order/img/share.png?t=1` / 화이트: `https://www.publog.co.kr/sub_order/img/share_w.png?t=1` |
| group-publog | 그룹코드 | PNG | 기본/블랙: `https://www.publog.co.kr/sub_order/img/share_group.png` / 화이트: `https://www.publog.co.kr/sub_order/img/share_group_w.png` |
