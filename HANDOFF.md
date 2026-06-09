# HANDOFF.md — 인수 인계 가이드

이 문서는 프로젝트를 처음 보는 사람(또는 한참 뒤의 운영자 본인)이 5분 안에 현재 상태를 파악하고 다음 작업을 이어갈 수 있도록 정리한 문서다.

## 1. 프로젝트 한 줄

- **무엇:** A.MAKERS 바이브 코딩 1:1 컨설팅 모집 랜딩페이지
- **목적:** 1기 5명 모집 (무료 상담 신청 폼 제출)
- **상태:** 코드 작성 완료, 자산 교체와 배포만 남음

## 2. 현재 진행 상태

- Phase 1~6 모두 완료 (총 11개 commit)
- 13섹션 콘텐츠 전체 작성됨 (index.html 1,500+ 라인)
- 폼·트래킹·OG·favicon은 placeholder 상태 (운영자가 키 발급 후 활성화)
- 자산 8개는 placeholder 박스 또는 SVG로 대체됨 (운영자가 실제 이미지 교체 필요)
- 헌법(`docs/PROJECT.md`)은 Phase 6 마지막 정리 commit으로 통합 정리된 상태

## 3. 파일 구조

```
/
├── index.html              # 메인 랜딩 (13섹션 전체, 폼·메타·트래킹 주석 포함)
├── style-guide.html        # 디자인 토큰 검증 (Phase 1 산출물, noindex)
├── thanks.html             # 폼 제출 완료 페이지
├── assets/
│   ├── images/             # 결과물 스크린샷 등 (현재 .gitkeep만, 운영자 자산 배치 위치)
│   └── og/
│       ├── og-image.svg    # OG 이미지 placeholder (1200×630)
│       └── favicon.svg     # favicon placeholder (32×32, "A")
├── docs/
│   ├── PROJECT.md          # 프로젝트 헌법 — 모든 의사결정의 단일 기준점
│   ├── phase1-instructions.md
│   ├── phase2-instructions.md
│   ├── phase3-instructions.md
│   ├── phase4-instructions.md
│   ├── phase5-instructions.md
│   └── phase6-instructions.md
├── HANDOFF.md              # 이 문서
├── README.md               # 프로젝트 설명 + 출시 전 체크리스트
└── .gitignore
```

### 파일별 역할

| 파일 | 역할 |
|---|---|
| `index.html` | 메인 랜딩. 모든 콘텐츠가 한 파일. 13섹션 + sticky 헤더 + 폼 + 메타·트래킹 |
| `style-guide.html` | 디자인 토큰 검증용 컴포넌트 카탈로그. 검색 색인 제외(noindex) |
| `thanks.html` | 폼 제출 후 redirect 도착 페이지. 동일 헤더 + 감사 카피 |
| `assets/images/` | 강사 사진·결과물 스크린샷·페르소나 시스템·히어로 비주얼 자리 |
| `assets/og/og-image.svg` | SNS 미리보기 이미지 placeholder. 실 출시 시 PNG 교체 권장 |
| `assets/og/favicon.svg` | 브라우저 탭 아이콘 placeholder |
| `docs/PROJECT.md` | **헌법** — 정체성·디자인·기술·콘텐츠 원칙. 가장 먼저 읽을 문서 |
| `docs/phase*-instructions.md` | 각 Phase 작업 지시서. 컨텍스트 파악에 유용 |
| `README.md` | 프로젝트 소개·실행 방법·Phase 진행표·출시 전 체크리스트 |

## 4. 작업 히스토리 (git log)

```
4c4ecd1 feat: phase 6 - 대상·가격·FAQ 완성 + 출시 준비
978afd1 docs: amend constitution - 컬러 시스템 통합 정리 + shadow 예외 명문화
afcfdbe feat: phase 5 - 커리큘럼 + 결과물 + 1:1 비교 구현
1378a0d feat: phase 4 - 문제 공감 + 통찰 + 비교 구현
3ec66ee docs: amend constitution - red/emerald 보조 단계 허용
eaff4ad feat: phase 3 - 강사 신뢰 + 페르소나 분석 시스템 구현
a197ee7 feat: phase 2 - 헤더, 히어로, 마지막 CTA 구현
5ead3f2 docs: amend constitution - 컬러 시스템 보조 단계 허용
8dde076 docs: amend constitution - 운영 브랜드 A.MAKERS로 확정
49d5276 feat: phase 1 - 골조 셋업 및 디자인 토큰 정의
06e9ff8 Initial commit
```

| # | 해시 | 메시지 | Phase |
|---|---|---|---|
| 1 | `06e9ff8` | Initial commit | — |
| 2 | `49d5276` | feat: phase 1 - 골조 셋업 및 디자인 토큰 정의 | 1 |
| 3 | `8dde076` | docs: amend constitution - 운영 브랜드 A.MAKERS로 확정 | 1.5 |
| 4 | `5ead3f2` | docs: amend constitution - 컬러 시스템 보조 단계 허용 | 2 사전 |
| 5 | `a197ee7` | feat: phase 2 - 헤더, 히어로, 마지막 CTA 구현 | 2 |
| 6 | `eaff4ad` | feat: phase 3 - 강사 신뢰 + 페르소나 분석 시스템 구현 | 3 |
| 7 | `3ec66ee` | docs: amend constitution - red/emerald 보조 단계 허용 | 4 사전 |
| 8 | `1378a0d` | feat: phase 4 - 문제 공감 + 통찰 + 비교 구현 | 4 |
| 9 | `afcfdbe` | feat: phase 5 - 커리큘럼 + 결과물 + 1:1 비교 구현 | 5 |
| 10 | `978afd1` | docs: amend constitution - 컬러 시스템 통합 정리 + shadow 예외 명문화 | 6 사전 |
| 11 | `4c4ecd1` | feat: phase 6 - 대상·가격·FAQ 완성 + 출시 준비 | 6 |

각 Phase 진입 시 헌법과 충돌이 있으면 사전 `docs: amend constitution` commit으로 분리해 처리. 헌법 §10 개정 절차 준수.

## 5. Phase별 작업 요약

### Phase 1 — 골조
- `index.html`, `style-guide.html`, `README.md` 셋업
- Tailwind CDN + Pretendard CDN 연결
- 13섹션 빈 골조 (id·배경·임시 제목·padding)
- 디자인 토큰 정의 (컬러 8박스/6종, 타이포 4단, 버튼 1, 카드 1)

### Phase 2 — 헤더 + 히어로 + 마지막 CTA
- sticky 미니헤더 (A.MAKERS 로고 + 1기 신청 small CTA)
- 섹션 1 `#hero`: 2칼럼 (좌 카피 + 우 비주얼 placeholder)
- 섹션 13 `#final-cta`: 네이비 + 인사이트 + 마감 압박 + CTA
- CTA 버튼 3종 변형 확립 (small / large / large+shadow)
- "플러스코치" → "A.MAKERS" 일괄 교체

### Phase 3 — 강사 신뢰 + 페르소나 시스템
- 섹션 5 `#instructor`: 강사 소개 + 결과물 갤러리 6장 (placeholder)
- 섹션 6 `#persona-system`: 100만 데이터 시스템 + 체크리스트 6
- `<html>`에 `scroll-pt-16` 추가 — sticky 헤더로 인한 anchor 가림 대응

### Phase 4 — 문제 공감 + 통찰 + 비교
- 섹션 2 `#problem`: 2×2 카드 4장 (호버 시 -translate-y-1)
- 섹션 3 `#insight`: 큰 헤드 + 본문·강조·클로징 3블록 + 구분선
- 섹션 4 `#comparison`: 좌우 비교 (붉은톤 5단계 vs 민트톤 5단계)

### Phase 5 — 커리큘럼 + 결과물 + 1:1 비교
- 섹션 7 `#roadmap`: Week 1~4 카드 (좌측 emerald 4px 보더)
- 섹션 8 `#outcomes`: 네이비 + 6항목 체크리스트 (emerald-400 SVG)
- 섹션 9 `#why-11`: 3열 비교 (회색 2 + 본 프로그램 강조 1: border-2 + shadow-lg + `lg:-mt-4`)

### Phase 6 — 대상 + 가격 + FAQ + 출시 준비
- 섹션 10 `#audience`: 추천 5 + 비추천 4 좌우 비교
- 섹션 11 `#pricing`: 가격 카드 (정가·할인가·포함 6·환불·CTA)
- 섹션 12 `#faq`: `<details>`/`<summary>` 아코디언 9개 (JS 없음)
- `#final-cta`에 인라인 신청 폼 (이름·연락처·소개 3필드 + submit)
- `thanks.html` 생성 (폼 redirect 도착지)
- 트래킹 코드 3종 placeholder (GA4·Meta Pixel·Microsoft Clarity)
- OG 이미지 SVG + favicon SVG 생성, head 메타 연결
- PROJECT.md §3.3 컬러 시스템 통합 정리, §3.5 shadow 예외 명문화

## 6. 헌법 (`docs/PROJECT.md`) 핵심

전체는 `docs/PROJECT.md` 참조. 가장 중요한 원칙만:

- **사이트의 단 하나의 목적**: "무료 상담 신청 폼 1건 제출" — 다른 모든 결정의 기준
- **디자인 톤**: Linear · Stripe · Notion + YC 액셀러레이터. GPT 강의 사이트 톤 금지
- **기술 스택 (고정)**: HTML/CSS/JS + Tailwind CDN + Pretendard CDN. 빌드 도구·npm·번들러 일체 금지
- **컬러 시스템**: 메인 7개 (white·slate-50·slate-900·slate-600·emerald-500/600·red-500) + 보조 단계 (Slate 100~800, Emerald 50/200/300/400, Red 50/200/300/400). 그 외 모든 색 금지
- **헌법 우선**: Phase 지시서와 충돌 시 헌법이 우선. 헌법 자체 개정은 §10 절차대로 별도 commit
- **Phase 외 작업 금지**: "기왕 하는 거 ~도 추가할까요" 금지. 의욕 폭주가 가장 큰 위험

## 7. 출시 전 남은 작업 (출시 체크리스트)

### 7.1 자산 교체 (8개)
- [ ] 강사 사진 → `assets/images/instructor.jpg`
- [ ] 결과물 스크린샷 6개 → `assets/images/result-1.png` ~ `result-6.png`
- [ ] 페르소나 분석 시스템 스크린샷 → `assets/images/persona-system.png`
- [ ] 히어로 우측 비주얼 → `assets/images/hero-visual.png`
- [ ] OG 이미지 PNG (1200×630) → `assets/og/og-image.png` (현재 SVG는 일부 SNS 미지원)
- [ ] favicon 실제 디자인 → `assets/og/favicon.svg` 또는 `.png`

자산 교체 후 `index.html`에서 placeholder 박스(`bg-gradient-to-br from-slate-100 to-slate-200`) 코드를 실제 `<img>` 태그로 교체 필요.

### 7.2 트래킹 키 발급 (3종 + 폼 이벤트)
- [ ] GA4 → analytics.google.com에서 측정 ID 발급 → `index.html`의 `G-XXXXXXXXXX` 치환 + 주석 해제
- [ ] Meta Pixel → business.facebook.com에서 ID 발급 → `YOUR_PIXEL_ID` 치환 + 주석 해제
- [ ] Microsoft Clarity → clarity.microsoft.com에서 ID 발급 → `YOUR_CLARITY_ID` 치환 + 주석 해제
- [ ] 폼 제출 이벤트 주석 활성화 (`gtag('event', 'lead_submit')`, `fbq('track', 'Lead')`)

### 7.3 폼 백엔드 (Formspree 권장)
- [ ] formspree.io 가입 → form ID 발급
- [ ] `index.html` 폼 `action` URL의 `YOUR_FORM_ID` 치환
- [ ] `thanks.html` redirect 동작 확인 (`_next` hidden 필드로 처리됨)

### 7.4 배포
- [ ] 도메인 구매 (`amakers.co.kr` 권장)
- [ ] Vercel 또는 GitHub Pages 연결
- [ ] DNS 설정 + HTTPS 확인
- [ ] 모바일·데스크탑 최종 점검 (375 / 768 / 1280)

### 7.5 미세 폴리싱 (선택)
- [ ] 폼 submit 버튼 `focus-visible:ring-offset-slate-900` → `ring-offset-white` (폼 카드 흰 배경 일치)
- [ ] 모바일 헤더 56px vs `scroll-pt-16`(64px) 8px 어긋남 → `scroll-pt-14 md:scroll-pt-16` 분기
- [ ] 섹션 9 모바일 박스 적층 순서 — 본 프로그램을 맨 위로 올릴지(`order-first lg:order-none`) 결정

## 8. 자주 묻는 질문 (작업 이어받는 사람 대상)

**Q. 코드 수정하려면 어떻게 시작?**
A. 프로젝트 폴더에서 `claude` 명령어로 Claude Code 실행. 첫 메시지에 "`docs/PROJECT.md`를 헌법으로 따른다. 작업 내용은 ..." 식으로 던지면 됨.

**Q. 새 Phase가 더 필요한가?**
A. 출시 자체에는 추가 Phase 불필요. 1기 운영 후 데이터(전환율·이탈 지점) 확보 시 2기 랜딩 개선이 다음 작업이 될 수 있음.

**Q. 빌드 명령어?**
A. 없음. 정적 HTML이라 `index.html`을 브라우저로 바로 열면 됨. 로컬 서버 원하면 `python -m http.server 8000`.

**Q. Tailwind 클래스가 안 먹는데?**
A. CDN 방식이라 빌드 없음. 새 클래스 안 먹으면 (1) 오타 확인, (2) `tailwind.config` 인라인 설정에서 막혔는지 확인, (3) Tailwind v3 임의 셀렉터 문법(`[&::...]:...`) 사용 시 따옴표 처리 확인.

**Q. 헌법 바꿔도 되나?**
A. `PROJECT.md` §10 절차대로. 별도 `docs: amend constitution - 사유` commit으로 분리. Phase 작업 commit에 헌법 변경을 섞지 말 것.

**Q. 폼 제출이 안 되는데?**
A. `index.html`의 `<form action="https://formspree.io/f/YOUR_FORM_ID">`가 placeholder. Formspree 계정 만들고 form ID 발급 후 치환 필요. 자체 백엔드 박을 수도 있음(Phase 6 범위 외).

**Q. 디자인 톤 바꾸고 싶다.**
A. `docs/PROJECT.md` §3 디자인 헌법 + §10 개정 절차 먼저 읽기. 톤 변경은 사업 모델 변경에 준하는 결정.

## 9. 다음 작업자에게 한마디

- **`docs/PROJECT.md` 먼저 읽어라.** 5분 투자가 며칠을 아낀다
- **Phase별 지시서**(`docs/phase*-instructions.md`)는 단순 참고용이 아니라 컨텍스트 자체. 1기 운영 후 2기 랜딩 만들 때 그대로 다시 활용 가능
- **디자인 톤(Linear · Stripe · Notion + YC) 절대 깨지 말 것.** 한 번 깨지면 사이트 전체 신뢰감이 무너진다
- **결제 마찰 제거(환불 보장·가격 명시·폼 3필드)는 의도된 설계.** 빼지 말 것
- **자산 교체할 때 placeholder 박스 코드까지 함께 정리.** `from-slate-100 to-slate-200` 그라데이션 박스는 자산 없는 동안의 임시 시각화. 실 이미지 들어오면 박스 div를 `<img>`로 통째 교체
- **카피 수정은 헌법 §5.2 핵심 카피에 영향 가는지 먼저 확인.** "4주 안에 AI로 첫 서비스 출시", "20%", "좋은 기획자"는 사업 컨셉 자체

## 10. 현재 디자인 단계 (2026-06-09 시점)

- **디자인은 완성본이 아니라 구성 단계.** 카피·섹션 흐름·배경 톤·카드 스타일은 모두 임시 결정이며 언제든 변경될 수 있다
- **디테일 폴리싱(여백 미세조정·호버 효과·그림자 톤 등)보다 카피·구조·섹션 흐름 결정을 우선한다.** 구성이 의미 있어야 디자인이 의미 있다
- 따라서 **헌법 §3.3 컬러 표·§3.5 디자인 금지 사항도 진행 중 빈번히 개정될 수 있는 임시 기준**. §10 개정 절차대로 별도 `docs: amend constitution` commit으로 분리해 처리한다
- 이 단계 중에는 운영자(A.MAKERS)의 카피·구조 변경 요청을 **헌법보다 우선**해 적용하고, 결과를 보고 헌법을 사후 정렬한다

## 11. 디자인 작업 캡쳐 검수 (운영자 명시 요청 시에만, 2026-06-11 정정)

직전(2026-06-09)에 박았던 "모든 디자인 작업 강제 캡쳐" 규칙은 폐기. 매 변경마다 4개 viewport 캡쳐 + 재수정 루프가 토큰 소모가 커서 운영자가 명시 요청한 경우에만 캡쳐 모드를 켠다.

**기본 동작:** 코드 변경 적용 + 정적 분석 기반 보고 (사이즈 추정·잘림 우려·요소 위치). 시각 검수는 운영자가 직접 브라우저로.

**캡쳐 모드 트리거:** "캡쳐해서 확인해줘", "스크린샷 검수해", "시안이랑 비교해서 맞춰줘" 같은 명시 표현.

**캡쳐 모드 절차 (트리거 받았을 때만):**
1. 시안 분석 — 글자 크기·간격·위치·톤·레이아웃 항목별 정리
2. 코드 적용
3. 헤드리스 캡쳐 (`captures/` 디렉토리, gitignore)
4. 시안과 비교
5. 차이 있으면 자동 재수정 최대 2회
6. 그래도 안 맞으면 운영자 확인 + 추가 가이드 요청

**저장 위치:** `captures/` 디렉토리 (gitignore). commit 안 함.
