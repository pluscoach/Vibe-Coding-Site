# Vibe Coding Site — Phase 1 작업 지시서

## 0. 프로젝트 컨텍스트 (반드시 먼저 읽기)

### 사업 배경
- 클라이언트: 플러스코치 (1인 사업자, 비전공자 출신)
- 사업소득 연 5,000만원 규모
- 주요 결과물:
  - 자동매매 프로그램 (MQL5, Python) — 크몽 단건 430만원 판매
  - BlogAutoFriends — AI 이웃 큐레이션 SaaS, 자체 결제·트래킹 운영 중
  - PageForge — Next.js 기반 상세페이지 자동 생성기
  - 캔들 릴스 자동 생성기 (Streamlit + moviepy)
  - 유튜브 자동 생성 파이프라인 (Remotion + Claude Code)
  - 텔레그램 AI 비서 Hermes (라즈베리파이 + LiveKit + Claude + Mem0)

### 이 사이트의 목적
바이브 코딩 1:1 컨설팅 프로그램의 **모집 랜딩페이지**.
- 4주 1:1 온라인 컨설팅
- 1기 한정 5명 모집, 정가 100만원 → 1기 50만원
- 목표 행동: "1:1 무료 상담 신청" 폼 제출
- 결제는 사전 상담 통화 후 진행

### 타겟 사용자
- 본업이 있는데 부수입을 만들고 싶은 직장인
- AI에 관심은 많지만 무엇을 만들지 모르는 사람
- 사업 아이템은 있는데 만드는 방법을 모르는 사장
- 코딩 강의 들었지만 실제로 뭘 만들지 못한 사람

### 사이트 컨셉
"GPT 강의 사이트가 아니라, Y Combinator에 지원하는 예비 창업자를 위한
SaaS 액셀러레이터 랜딩페이지" 톤.

레퍼런스: Linear, Stripe, Notion의 미니멀·신뢰감 있는 톤.

---

## 1. 기술 스택 (확정됨)

- **HTML/CSS/JS 정적 1페이지**
- **Tailwind CSS — CDN 방식** (`<script src="https://cdn.tailwindcss.com"></script>`)
- **빌드 도구 없음.** 그냥 `index.html` 하나로 시작
- **Pretendard 폰트** (CDN으로 로드)
- **반응형 필수** (데스크탑·태블릿·모바일)
- 추가 라이브러리는 꼭 필요한 경우에만 도입, 그때마다 확인

### 폴더 구조 (Phase 1 종료 시점)
```
/
├── index.html           # 메인 페이지 (모든 섹션 한 파일에)
├── assets/
│   ├── images/          # 결과물 스크린샷 등
│   └── og/              # OG 이미지
├── README.md            # 프로젝트 설명
└── .gitignore           # 이미 있음 (Node 템플릿)
```

---

## 2. 디자인 시스템 (Phase 1에서 확정해야 할 것)

### 컬러 토큰
Tailwind 기본 팔레트에서 다음으로 한정:

| 용도 | 컬러 | Tailwind 클래스 |
|---|---|---|
| 기본 배경 | 화이트 | `bg-white` |
| 보조 배경 (회색 톤 섹션) | #F8FAFC | `bg-slate-50` |
| 강조 배경 (네이비 섹션) | #0F172A | `bg-slate-900` |
| 본문 텍스트 | #0F172A | `text-slate-900` |
| 보조 텍스트 | #475569 | `text-slate-600` |
| CTA 강조 컬러 | 민트 계열 | `bg-emerald-500` / `bg-emerald-600` |
| 위험·경고 (기존 방식 비교) | 레드 톤 | `text-red-500` 정도 |

**이외 컬러 사용 금지.** 3색 + 보조 회색 + 1포인트(민트) 이상은 톤이 깨짐.

### 타이포그래피
- 폰트: Pretendard (CDN)
- 헤드라인: 56~64px, font-weight 700~800
- 서브헤드: 24~28px, font-weight 500
- 본문: 16~18px, font-weight 400
- 캡션: 14px, font-weight 400

### 여백 원칙
- 섹션 간 vertical padding: 데스크탑 `py-24` ~ `py-32`, 모바일 `py-16`
- 컨테이너 최대 너비: `max-w-6xl` 또는 `max-w-7xl`
- 좌우 padding: `px-6` 모바일, `px-8` 데스크탑

### 금지 사항
- 이모지 사용 금지 (✓ 체크마크 SVG는 OK)
- 그라데이션 과도하게 쓰지 말 것 (1~2군데만 포인트)
- 박스 그림자 너무 진하게 쓰지 말 것 (`shadow-md` 정도까지)
- 둥근 모서리 과하게 쓰지 말 것 (`rounded-2xl` 기본)
- 강의 사이트 분위기 금지 (네온·과한 컬러·"수강신청!" 같은 흥분 톤 X)

---

## 3. Phase 1 작업 범위

이번 Phase에서 만들 것:

### (1) 프로젝트 셋업
- `index.html` 생성
- Tailwind CDN, Pretendard 폰트 CDN 연결
- 기본 `<meta>` 태그 (charset, viewport, description, og:*)
- favicon 자리만 잡아둠 (실제 파일은 나중에)

### (2) 13개 섹션의 빈 골조
각 섹션을 `<section id="...">` 로 자리만 잡되, 안에는:
- 섹션 제목만 임시로 박아둠 (예: `<h2>섹션 1 — 히어로</h2>`)
- 섹션 배경색만 설계대로 적용
- 적절한 padding 적용

이렇게 하는 이유: 전체 흐름이 한눈에 보이고, 섹션 배경 전환이 자연스러운지 확인 가능.

### (3) 섹션 ID와 배경 매핑

| 순번 | 섹션 ID | 섹션 이름 | 배경 |
|---|---|---|---|
| 1 | `hero` | 히어로 | `bg-white` |
| 2 | `problem` | 문제 공감 | `bg-slate-50` |
| 3 | `insight` | 통찰 (20% 카피) | `bg-white` |
| 4 | `comparison` | 기존 vs 우리 방식 | `bg-slate-50` |
| 5 | `instructor` | 강사 신뢰 | `bg-white` |
| 6 | `persona-system` | 페르소나 분석 시스템 | `bg-slate-50` |
| 7 | `roadmap` | 4주 로드맵 | `bg-white` |
| 8 | `outcomes` | 4주 후 결과물 | `bg-slate-900` (네이비) |
| 9 | `why-11` | 왜 1:1인가 | `bg-white` |
| 10 | `audience` | 추천/비추천 대상 | `bg-slate-50` |
| 11 | `pricing` | 가격 + 보장 | `bg-white` |
| 12 | `faq` | FAQ | `bg-slate-50` |
| 13 | `final-cta` | 마지막 CTA | `bg-slate-900` (네이비) |

### (4) 디자인 토큰 검증용 컴포넌트
페이지 맨 아래(또는 별도 `style-guide.html`)에 임시로:
- 색상 팔레트 6개
- 타이포 샘플 (헤드라인 / 서브 / 본문 / 캡션)
- 버튼 컴포넌트 1개 (Primary CTA)
- 카드 컴포넌트 1개 (호버 효과 포함)

→ Phase 2부터 실제 섹션 만들 때 이 토큰을 기준으로 작업.
→ Phase 1 검수 후에는 이 영역 제거 또는 주석 처리.

### (5) 메타 정보
```html
<title>플러스코치 바이브 코딩 1:1 — 4주 안에 AI로 첫 서비스 출시</title>
<meta name="description" content="개발 경험이 없어도 괜찮습니다. 시장 검증부터 MVP 제작, 출시까지 4주 1:1로 함께 진행합니다.">
<meta property="og:title" content="플러스코치 바이브 코딩 1:1">
<meta property="og:description" content="4주 안에 AI로 당신의 첫 서비스를 출시하세요">
<meta property="og:type" content="website">
```

### (6) README.md
프로젝트 설명, 실행 방법(그냥 index.html 열기), Phase 진행 상태 기록.

---

## 4. 완료 판정 체크리스트

Phase 1이 끝났다고 판단하는 기준:

- [ ] `index.html` 열면 13개 섹션이 위아래로 배치되어 있고, 각 섹션 배경색이 디자인대로 적용됨
- [ ] 화이트·슬레이트50·슬레이트900 세 배경이 교차되며 자연스럽게 전환됨
- [ ] 모바일(375px), 태블릿(768px), 데스크탑(1280px) 세 너비에서 깨지지 않음
- [ ] Pretendard 폰트가 정상 로드됨 (개발자 도구로 확인)
- [ ] Tailwind 클래스가 정상 작동함 (배경색 적용으로 확인)
- [ ] 디자인 토큰 검증 영역에 6개 컬러, 4개 타이포, 1개 버튼, 1개 카드가 보임
- [ ] `<title>`, `<meta description>`, OG 태그 모두 박혀있음
- [ ] README.md에 Phase 진행 상태 적혀있음
- [ ] git commit 완료 (`feat: phase 1 - 골조 셋업 및 디자인 토큰 정의`)

---

## 5. 작업 순서 권장

1. `index.html` 생성, Tailwind/Pretendard CDN 연결
2. 메타 태그 작성
3. 13개 섹션 골조 작성 (id, 배경, 임시 제목)
4. 디자인 토큰 검증 영역 작성
5. 데스크탑·태블릿·모바일 너비에서 확인
6. README.md 작성
7. git add, commit

---

## 6. 작업 중 판단해야 할 것

- 디자인 토큰 검증 영역을 `index.html`에 임시로 넣을지, 별도 `style-guide.html`로 분리할지 → **판단해서 결정. 권장: 별도 `style-guide.html`로 분리** (메인 페이지가 더러워지지 않게)
- Pretendard CDN 주소는 공식 권장 방식 사용 (`https://cdn.jsdelivr.net/gh/orioncactus/pretendard/.../variable/...`)
- Tailwind CDN의 한계상 커스텀 폰트 적용은 `tailwind.config` 인라인 설정으로 처리

---

## 7. Phase 1에서 절대 하지 말 것

- 각 섹션의 실제 내용 채우기 (Phase 2 이후 작업)
- 결과물 스크린샷 추가 (자료 준비되면 Phase 3에서)
- 폼 제출 로직 (Phase 6에서)
- 자바스크립트 인터랙션 (스크롤 애니메이션 등) — Phase 5~6에서
- 빌드 도구 도입 (npm init, webpack, vite 등 일체 금지)
- 추가 패키지 설치

---

## 8. 작업 끝나면 보고할 것

Phase 1 완료 후 다음을 보고:

1. `index.html`을 브라우저에서 연 스크린샷 3장
   - 데스크탑 (전체 스크롤한 모습)
   - 모바일 (전체 스크롤한 모습)
   - 디자인 토큰 검증 영역 (또는 style-guide.html)

2. 작업 중 판단한 결정 사항 정리
   - 디자인 토큰 분리 여부
   - Pretendard 로드 방식
   - 기타 즉흥 결정한 것

3. Phase 2 작업 전 짚어야 할 이슈 (있다면)

---

자, 이제 작업 시작.
