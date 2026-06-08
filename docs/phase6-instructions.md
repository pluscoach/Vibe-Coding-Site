# Phase 6 작업 지시서 — 대상 + 가격 + FAQ + 폼·트래킹·폴리싱

## 0. 이번 Phase의 의미

마지막 Phase. 두 가지 일을 동시에 한다:
1. **콘텐츠 마무리** — 섹션 10(대상), 11(가격), 12(FAQ) 완성
2. **출시 준비** — 폼 제출 흐름, 트래킹 코드 자리, OG 이미지 자리, 헌법 정리

이번 Phase가 끝나면 사이트는 **출시 가능 상태**가 된다. 자산(실제 이미지) 교체와 도메인 연결만 남음.

## 1. 작업 범위

### 1.1 신규 콘텐츠
- [ ] 섹션 10 (`#audience`) — 추천/비추천 대상
- [ ] 섹션 11 (`#pricing`) — 가격 + 포함사항 + 환불 보장
- [ ] 섹션 12 (`#faq`) — 자주 묻는 질문 9개 (아코디언)

### 1.2 출시 준비 작업
- [ ] 마지막 CTA 섹션(`#final-cta`)에 인라인 신청 폼 추가
- [ ] 폼 제출 처리 — Formspree 또는 Google Forms 임시 연결 (실제 키는 placeholder)
- [ ] 트래킹 코드 자리 (GA4, Meta Pixel, Microsoft Clarity) — 주석으로 자리만, 실제 키는 placeholder
- [ ] OG 이미지 placeholder 처리 (`/assets/og/og-image.png` 자리, 임시 SVG로 대체)
- [ ] favicon placeholder (`/assets/og/favicon.svg` 단순 텍스트 SVG)

### 1.3 헌법·문서 정리
- [ ] PROJECT.md §3.3 컬러 시스템 통합 정리 (Phase 2·4 미세 개정 누적분 통합)
- [ ] PROJECT.md §3.5 디자인 금지 사항에 "강조 위치 shadow-lg 예외 허용" 명문화
- [ ] README.md 최종 갱신 (Phase 6 완료, 출시 전 체크리스트)

### 1.4 의도적으로 안 할 것
- 실제 트래킹 키 박기 (placeholder만)
- 실제 Formspree 키 박기 (placeholder만)
- 실제 OG 이미지·favicon·결과물 스크린샷 (자산 준비 후 별도 commit)
- 도메인 연결 (DNS, Vercel/GitHub Pages 설정)
- 스크롤 애니메이션 도입 (정적 신뢰감 유지)

## 2. 섹션 10 — 추천/비추천 대상 (#audience)

### 2.1 레이아웃
```
┌──────────────────────────────────────────────────┐
│ (슬레이트50 배경)                                │
│                                                  │
│   [좌우 2칼럼 비교]                              │
│   ┌─────────────────┐  ┌─────────────────┐       │
│   │ 추천 대상 ✓     │  │ 비추천 대상 ✗   │       │
│   │ (emerald 톤)    │  │ (red 톤)        │       │
│   │                 │  │                 │       │
│   │ ✓ 항목 5개      │  │ ✗ 항목 4개      │       │
│   └─────────────────┘  └─────────────────┘       │
│                                                  │
└──────────────────────────────────────────────────┘
```

### 2.2 박스 디자인

**그리드:**
- 데스크탑: `grid grid-cols-2 gap-6 md:gap-8`
- 모바일: `grid grid-cols-1 gap-4`

**박스 공통:**
- 배경: `bg-white`
- 모서리: `rounded-2xl`
- 패딩: `p-8 md:p-10`

**좌측 박스 (추천):**
- 보더: `border border-emerald-200 border-t-4 border-t-emerald-500`

**우측 박스 (비추천):**
- 보더: `border border-red-200 border-t-4 border-t-red-400`

### 2.3 박스 헤더

**좌측 헤더:**
```
이런 분께 추천합니다
```
- 폰트: `text-2xl md:text-3xl font-bold text-emerald-600`
- 정렬: `text-center`
- 하단 여백: `mb-8`

**우측 헤더:**
```
이런 분께는 권하지 않습니다
```
- 폰트: `text-2xl md:text-3xl font-bold text-red-500`
- 정렬: `text-center`
- 하단 여백: `mb-8`

### 2.4 추천 항목 5개 (확정)
1. 본업이 있는데 부수입을 만들고 싶은 직장인
2. AI에 관심은 많지만 무엇을 만들지 모르는 분
3. 사업 아이템은 있는데 만드는 방법을 모르는 사장
4. 코딩 강의 들었지만 실제로 뭘 만들지 못한 분
5. 매주 4~6시간 투자할 수 있는 분

**디자인:**
- 각 항목 좌측에 ✓ SVG (emerald-500)
- 텍스트: `text-base md:text-lg text-slate-700`
- 정렬: `flex items-start gap-3`
- 항목 간 간격: `space-y-4`

### 2.5 비추천 항목 4개 (확정)
1. 단기간에 돈만 벌고 싶은 분
2. 직접 실행할 의지가 없는 분
3. AI가 다 해줄 거라 기대하는 분
4. 코딩 자체를 깊게 배우고 싶은 분 (여긴 사업 코스)

**디자인:**
- 각 항목 좌측에 ✗ SVG (red-400)
- 텍스트: `text-base md:text-lg text-slate-700`
- 정렬: `flex items-start gap-3`
- 항목 간 간격: `space-y-4`

**✗ SVG:**
```html
<svg class="w-5 h-5 text-red-400 flex-shrink-0 mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M6 18L18 6M6 6l12 12"></path>
</svg>
```

### 2.6 섹션 패딩
- 섹션: `py-24 md:py-32`
- 컨테이너: `max-w-5xl mx-auto px-6 md:px-8`

## 3. 섹션 11 — 가격 + 보장 (#pricing)

### 3.1 레이아웃
```
┌──────────────────────────────────────────────────┐
│ (화이트 배경)                                    │
│                                                  │
│   [중앙 정렬, 카드 형태]                         │
│   ┌────────────────────────────┐                 │
│   │ 1기 모집 — 한정 5명         │                 │
│   │                            │                 │
│   │ 정가 100만원                │                 │
│   │ → 1기 한정 50만원           │                 │
│   │                            │                 │
│   │ ─────────                  │                 │
│   │                            │                 │
│   │ 포함 사항 6개              │                 │
│   │                            │                 │
│   │ ─────────                  │                 │
│   │                            │                 │
│   │ 환불 보장 안내              │                 │
│   └────────────────────────────┘                 │
│                                                  │
└──────────────────────────────────────────────────┘
```

### 3.2 가격 카드 디자인
- 배경: `bg-white`
- 보더: `border-2 border-emerald-500`
- 모서리: `rounded-2xl`
- 패딩: `p-8 md:p-12`
- 그림자: `shadow-lg`
- 컨테이너: `max-w-3xl mx-auto`

### 3.3 카드 상단 — 모집 라벨
```
1기 모집 — 한정 5명
```
- 폰트: `text-sm md:text-base font-semibold text-emerald-600`
- 정렬: `text-center`
- 하단 여백: `mb-6`

### 3.4 카드 중단 — 가격 표시

**정가 (취소선):**
```
정가 100만원
```
- 폰트: `text-xl text-slate-400 line-through`
- 정렬: `text-center`

**할인가 (강조):**
```
→ 1기 한정 50만원
```
- 폰트: `text-4xl md:text-5xl font-bold text-slate-900`
- "50만원" 부분만 `text-emerald-600`
- 정렬: `text-center`
- 상단 여백: `mt-2`

**부가 안내:**
```
2기부터 정가 적용
1기는 후기 작성 협조해주시는 분 우선
```
- 폰트: `text-sm text-slate-500`
- 정렬: `text-center`
- 상단 여백: `mt-4`

### 3.5 구분선
- `<div class="border-t border-slate-200 my-10"></div>`

### 3.6 포함 사항 섹션

**제목:**
```
포함 사항
```
- 폰트: `text-lg font-bold text-slate-900`
- 정렬: `text-center`
- 하단 여백: `mb-6`

**6개 항목 (확정):**
1. 4주 1:1 온라인 컨설팅 (주 2시간 × 4회)
2. 사전 학습 자료 (영상 + PDF)
3. 강의 기간 내 카톡 상담 무제한
4. 100만 데이터 페르소나 분석 사이트 이용권
5. 1,000만원 수익 설계 시스템 문서
6. 종강 후 1개월 애프터 (질문 응답)

**디자인:**
- 각 항목 ✓ SVG (emerald-500, `w-5 h-5`)
- 텍스트: `text-base text-slate-700`
- 정렬: `flex items-start gap-3`
- 항목 간 간격: `space-y-3`

### 3.7 환불 보장 섹션 (구분선 후)

**제목:**
```
환불 보장
```
- 폰트: `text-lg font-bold text-slate-900`
- 정렬: `text-center`
- 하단 여백: `mb-4`

**본문:**
```
1주차 진행 후
"이 프로그램이 나와 맞지 않는다" 판단되시면
전액 환불해드립니다.
```
- 폰트: `text-base md:text-lg text-slate-700 leading-relaxed`
- 정렬: `text-center`

### 3.8 카드 하단 — CTA 버튼
- 텍스트: `1기 무료 상담 신청`
- 디자인: 히어로 large CTA와 동일 (`px-8 py-4 text-lg bg-emerald-600 hover:bg-emerald-700`)
- 링크: `href="#final-cta"`
- 정렬: `flex justify-center`
- 상단 여백: `mt-10`

### 3.9 섹션 패딩
- 섹션: `py-24 md:py-32`
- 컨테이너: `max-w-4xl mx-auto px-6 md:px-8`

## 4. 섹션 12 — FAQ (#faq)

### 4.1 레이아웃
```
┌──────────────────────────────────────────────────┐
│ (슬레이트50 배경)                                │
│                                                  │
│   [섹션 헤드 — 중앙 정렬]                        │
│   "자주 묻는 질문"                               │
│                                                  │
│   [아코디언 9개]                                 │
│   ▶ Q. 개발을 정말 하나도 몰라도 되나요?        │
│   ▶ Q. 사업 아이템이 없어도 되나요?              │
│   ...                                            │
│                                                  │
└──────────────────────────────────────────────────┘
```

### 4.2 섹션 헤드
```
자주 묻는 질문
```
- 폰트: `text-4xl md:text-5xl font-bold text-slate-900`
- 정렬: `text-center`
- 하단 여백: `mb-16`

### 4.3 아코디언 구현 방식

**`<details>`/`<summary>` HTML 표준 태그 사용. JS 불필요.**

각 FAQ 아이템:
```html
<details class="group bg-white border border-slate-200 rounded-xl overflow-hidden">
  <summary class="cursor-pointer p-6 flex items-center justify-between font-semibold text-slate-900 hover:bg-slate-50 transition">
    <span class="text-base md:text-lg">Q. 개발을 정말 하나도 몰라도 되나요?</span>
    <svg class="w-5 h-5 text-slate-400 transition group-open:rotate-180 flex-shrink-0 ml-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" aria-hidden="true">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
    </svg>
  </summary>
  <div class="px-6 pb-6 text-base text-slate-600 leading-relaxed">
    네. AI와 협업하는 법을 배우는 것이 목적입니다. 1기 수강생 중에도 비전공자가 많습니다.
  </div>
</details>
```

**아이템 간 간격:** `space-y-3`

### 4.4 FAQ 9개 (확정)

| # | 질문 | 답변 |
|---|---|---|
| 1 | 개발을 정말 하나도 몰라도 되나요? | 네. AI와 협업하는 법을 배우는 것이 목적입니다. 1기 수강생 중에도 비전공자가 많습니다. |
| 2 | 사업 아이템이 없어도 되나요? | 네. 1주차에서 함께 찾습니다. |
| 3 | 어떤 AI를 사용하나요? | Claude · ChatGPT · Cursor · Claude Code. 상황에 따라 다릅니다. |
| 4 | AI 구독료는 별도인가요? | 네. Claude 또는 ChatGPT 유료 결제를 권장합니다 (월 2~3만원). 첫 주에는 무료 버전으로도 가능합니다. |
| 5 | 매주 시간을 얼마나 써야 하나요? | 주 1회 1:1 줌 2시간 + 숙제 2~4시간. 총 주 4~6시간 정도 필요합니다. |
| 6 | 회사 다니면서 가능한가요? | 네. 줌 일정은 협의 가능합니다. 숙제는 평일 저녁·주말로 진행 가능합니다. |
| 7 | 컴퓨터 사양은 어느 정도 필요한가요? | 인터넷 되는 노트북이면 충분합니다. 특별한 사양 필요 없습니다. |
| 8 | 4주 안에 정말 결제까지 받을 수 있나요? | 목표는 "첫 결제 시도"입니다. 실제 결제 성공은 아이템에 따라 다르며, 결제 시도 자체가 가장 중요한 검증입니다. |
| 9 | 환불 조건은 어떻게 되나요? | 1주차 진행 후 안 맞다고 판단되시면 전액 환불해드립니다. 2주차 이후는 환불 불가입니다. |

### 4.5 섹션 패딩
- 섹션: `py-24 md:py-32`
- 컨테이너: `max-w-3xl mx-auto px-6 md:px-8`

## 5. 마지막 CTA 섹션에 인라인 폼 추가 (#final-cta)

### 5.1 위치
기존 #final-cta 섹션의 CTA 버튼 **위 또는 아래**에 인라인 폼 추가.

권장: **CTA 버튼이 폼의 제출 버튼이 되도록** 통합. 즉 폼 위에 안내 + 입력 필드 3개 + 제출 버튼(기존 CTA).

### 5.2 폼 디자인
```
┌──────────────────────────────────────────────────┐
│ (네이비 배경 위 흰 카드)                         │
│                                                  │
│   ┌─────────────────────────┐                    │
│   │ 이름                    │                    │
│   ├─────────────────────────┤                    │
│   │ 연락처 (이메일 또는 폰) │                    │
│   ├─────────────────────────┤                    │
│   │ 간단한 자기소개         │                    │
│   │ (어떤 일을 하고 계신지) │                    │
│   │ ── 텍스트영역 ──        │                    │
│   └─────────────────────────┘                    │
│                                                  │
│   [ 1기 무료 상담 신청 ]                         │
│                                                  │
│   신청 후 사전 통화로 핏 맞춰본 뒤              │
│   결제 진행됩니다.                               │
└──────────────────────────────────────────────────┘
```

### 5.3 폼 컨테이너
- 배경: `bg-white`
- 모서리: `rounded-2xl`
- 패딩: `p-6 md:p-8`
- 최대 너비: `max-w-lg mx-auto`
- 상단 여백: 기존 마감 압박 카피 아래에 `mt-12`

### 5.4 입력 필드

**공통:**
- 입력 박스: `w-full px-4 py-3 border border-slate-300 rounded-lg text-slate-900 focus:outline-none focus:border-emerald-500 focus:ring-2 focus:ring-emerald-200 transition`
- 라벨 (필드 위, 작게): `text-sm font-medium text-slate-700 mb-1 block`

**필드 1 — 이름:**
- 라벨: "이름"
- type: text
- name: name
- required

**필드 2 — 연락처:**
- 라벨: "연락처 (이메일 또는 휴대폰)"
- type: text
- name: contact
- required

**필드 3 — 간단 소개:**
- 라벨: "어떤 일을 하고 계신가요? (선택)"
- textarea, rows="3"
- name: intro
- 선택 항목

**필드 간 간격:** `space-y-4`

### 5.5 폼 제출 처리

**임시: Formspree 또는 Google Forms 사용. 실제 키는 placeholder.**

권장 방식:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="...">
```

**또는 더 간단한 방식 — Netlify Forms 호환 placeholder:**
```html
<form action="#" method="POST" data-form="signup" class="...">
  <input type="hidden" name="form-name" value="signup">
  <!-- 필드들 -->
</form>
```

**선택:** 너 자체 BlogAutoFriends·자동매매 사이트 운영 경험으로 자체 백엔드 박을 수도 있음. 그건 Phase 6 범위 외. 일단 placeholder.

### 5.6 제출 버튼
- 기존 마지막 CTA 버튼을 폼의 `<button type="submit">`으로 전환
- 디자인 그대로 (`px-8 py-4 text-lg bg-emerald-600 hover:bg-emerald-700 shadow-xl rounded-xl`)
- `w-full` 추가해서 폼 너비 채움
- 텍스트: `1기 무료 상담 신청`

### 5.7 폼 아래 안내
기존 CTA 안내 카피 유지:
```
신청 후 사전 통화로 핏 맞춰본 뒤
결제 진행됩니다.
```
- 폰트: `text-sm text-slate-400`
- 정렬: `text-center`
- 상단 여백: `mt-6`

### 5.8 폼 제출 후 처리 (간단)
- 별도 thanks.html 페이지 생성 → 폼 action을 `/thanks.html`로 두거나
- 또는 JS 없이 그냥 Formspree 기본 redirect 사용
- thanks.html은 간단히: "신청 감사합니다. 1~2일 내 연락드리겠습니다." + 메인으로 돌아가는 링크

**thanks.html 생성 — Phase 1 디자인 토큰 그대로 사용. 헤더 동일.**

## 6. 트래킹 코드 자리 (Placeholder)

### 6.1 `<head>` 안에 주석으로 자리만

```html
<!-- Google Analytics 4 -->
<!--
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
-->

<!-- Meta Pixel -->
<!--
<script>
  !function(f,b,e,v,n,t,s){...}('init', 'YOUR_PIXEL_ID');
  fbq('track', 'PageView');
</script>
-->

<!-- Microsoft Clarity -->
<!--
<script type="text/javascript">
  (function(c,l,a,r,i,t,y){...})(window, document, "clarity", "script", "YOUR_CLARITY_ID");
</script>
-->
```

**실제 키 박지 말 것.** 운영자가 키 받아서 주석 해제하면 동작하도록.

### 6.2 폼 제출 이벤트 자리 (주석)
```html
<!-- 폼 제출 시 트래킹 이벤트 (실제 구현은 키 박힌 후) -->
<!--
gtag('event', 'lead_submit', { event_category: 'form' });
fbq('track', 'Lead');
-->
```

## 7. OG 이미지 + Favicon Placeholder

### 7.1 OG 이미지

**자산 파일 없음 — 임시 SVG 또는 placeholder 처리.**

옵션 A — `<meta property="og:image">` 태그 박지 않음 (Phase 2 결정 그대로 유지).

옵션 B — assets/og/og-image.svg를 단순 텍스트 SVG로 생성:
```html
<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="630" viewBox="0 0 1200 630">
  <rect width="1200" height="630" fill="#0F172A"/>
  <text x="600" y="280" font-size="64" font-weight="800" fill="white" text-anchor="middle">A.MAKERS</text>
  <text x="600" y="360" font-size="32" fill="#94A3B8" text-anchor="middle">4주 안에 AI로 첫 서비스 출시</text>
</svg>
```

**권장: 옵션 B.** 자산이 준비되기 전 SNS 공유 시 빈 화면 안 뜸. `<meta property="og:image" content="/assets/og/og-image.svg">` 추가.

### 7.2 Favicon

assets/og/favicon.svg를 단순 SVG로 생성:
```html
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
  <rect width="32" height="32" rx="6" fill="#0F172A"/>
  <text x="16" y="22" font-size="18" font-weight="800" fill="white" text-anchor="middle" font-family="system-ui">A</text>
</svg>
```

`<link rel="icon" type="image/svg+xml" href="/assets/og/favicon.svg">` 추가.

## 8. PROJECT.md 헌법 정리

### 8.1 §3.3 컬러 시스템 통합 정리

Phase 2, 4에서 누적된 미세 개정을 한 표로 통합:

```markdown
### 3.3 컬러 시스템 (확정)

#### 메인 컬러
| 용도 | 컬러 | Tailwind |
|---|---|---|
| 기본 배경 | 화이트 | `bg-white` |
| 보조 배경 | #F8FAFC | `bg-slate-50` |
| 강조 배경 | #0F172A | `bg-slate-900` |
| 본문 텍스트 | #0F172A | `text-slate-900` |
| 보조 텍스트 | #475569 | `text-slate-600` |
| 포인트 컬러 | 민트 | `bg-emerald-500` / `bg-emerald-600` |
| 위험 표시 | 레드 | `text-red-500` |

#### 허용 보조 단계
| 색 계열 | 허용 단계 | 사용 목적 |
|---|---|---|
| Slate | 100, 200, 300, 400, 500, 700, 800 | 보더·구분선·캡션·미세 카피·네이비 위 보조 |
| Emerald | 50, 200, 300, 400, 600, 700 | 호버 강조·CTA·체크리스트·박스 강조 |
| Red | 50, 200, 300, 400, 500 | 비추천·기존 방식 비교 박스 |

#### 금지
위 표 외 모든 색 단계, 모든 다른 색상.
```

### 8.2 §3.5 shadow-lg 예외 명문화

기존 "shadow-md 이하" 항목 아래에 한 줄 추가:
```markdown
- 단 핵심 CTA 버튼, 가격 카드, 본 프로그램 비교 박스 등 시각 강조가 필요한 위치에서는 shadow-lg / shadow-xl 사용 허용
```

### 8.3 commit 분리
- `docs: amend constitution - 컬러 시스템 통합 정리`
- `docs: amend constitution - shadow 예외 명문화`

또는 한 commit으로 묶어도 OK. 판단해서 진행.

## 9. README.md 최종 갱신

다음 섹션 추가:

```markdown
## 출시 전 체크리스트

자산 교체:
- [ ] 강사 사진 (assets/images/instructor.jpg)
- [ ] 결과물 스크린샷 6개 (assets/images/result-1.png ~ result-6.png)
- [ ] 페르소나 분석 시스템 스크린샷 (assets/images/persona-system.png)
- [ ] 히어로 우측 비주얼 (assets/images/hero-visual.png)
- [ ] OG 이미지 실제 이미지로 교체 (assets/og/og-image.png)
- [ ] favicon 실제 디자인으로 교체 (assets/og/favicon.svg)

트래킹 코드:
- [ ] GA4 측정 ID 발급 + index.html 주석 해제
- [ ] Meta Pixel ID 발급 + 주석 해제
- [ ] Microsoft Clarity ID 발급 + 주석 해제

폼 제출:
- [ ] Formspree 또는 자체 백엔드 키 발급
- [ ] 폼 action URL 교체
- [ ] thanks.html 동작 확인

배포:
- [ ] 도메인 결정 (amakers.co.kr 권장)
- [ ] Vercel 또는 GitHub Pages 연결
- [ ] DNS 설정
- [ ] HTTPS 확인
- [ ] 모바일·데스크탑 최종 점검
```

## 10. 완료 판정 체크리스트

- [ ] 섹션 10 추천/비추천 박스 2개 (5+4 항목)
- [ ] 섹션 11 가격 카드 (정가·할인가·포함사항 6·환불 보장·CTA)
- [ ] 섹션 12 FAQ 9개 아코디언 (`<details>`/`<summary>`)
- [ ] FAQ 아코디언 클릭 시 펼침/접힘 정상, 아이콘 회전
- [ ] 마지막 CTA에 인라인 폼 (필드 3개 + 제출 버튼)
- [ ] thanks.html 생성
- [ ] 트래킹 코드 주석 placeholder 박힘
- [ ] OG 이미지 SVG + favicon SVG 생성, 메타 태그 연결
- [ ] PROJECT.md 컬러 시스템 통합 정리
- [ ] PROJECT.md shadow 예외 명문화
- [ ] README.md 출시 전 체크리스트 추가
- [ ] 헤더 우측 "1기 신청" 정상
- [ ] 375/768/1280 깨짐 없음
- [ ] 가로 스크롤 없음
- [ ] 전체 페이지 시각적 일관성 점검 (13섹션 톤·여백·CTA 디자인)
- [ ] git commit 완료 (메시지: `feat: phase 6 - 대상·가격·FAQ 완성 + 출시 준비`)

## 11. 작업 끝나면 보고할 것

1. 만든/수정한 파일 목록
2. 즉흥 결정 사항
3. 체크리스트 항목별 통과 여부
4. 출시 전 남은 작업 정리 (자산·트래킹·도메인)
5. 전체 사이트 최종 평가 (글 설명) — 13섹션 톤 일관성, 결제 마찰 제거 정도, 신뢰감 수준
