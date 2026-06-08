# 바이브 코딩 1:1 컨설팅 랜딩페이지

A.MAKERS 바이브 코딩 1:1 컨설팅 모집 랜딩페이지

목적은 단 하나 — **"1기 무료 상담 신청 폼 1건 제출"**. 자세한 정의·디자인·기술 헌법은 [`docs/PROJECT.md`](docs/PROJECT.md) 참고.

## 실행

빌드 도구 없음. `index.html`을 브라우저로 열면 끝.

- `index.html` — 메인 랜딩 (13섹션 단일 페이지)
- `style-guide.html` — 디자인 토큰 검증 (Phase 1 산출물, 검색 색인 제외)

Tailwind CSS와 Pretendard 폰트는 CDN으로 로드.

## 폴더 구조

```
/
├── index.html              # 메인 랜딩 (13섹션)
├── style-guide.html        # 디자인 토큰 검증 페이지
├── assets/
│   ├── images/             # 결과물 스크린샷 등 (Phase 3~)
│   └── og/                 # OG 이미지, favicon (Phase 6)
├── docs/
│   ├── PROJECT.md          # 프로젝트 헌법
│   └── phase1-instructions.md
├── README.md
└── .gitignore
```

## Phase 진행 상태

| Phase | 범위 | 상태 |
|---|---|---|
| Phase 1 | 셋업 + 13섹션 골조 + 디자인 토큰 | **진행 완료** |
| Phase 2 | 헤더 + 히어로 + 마지막 CTA (섹션 1, 13) | **진행 완료** |
| Phase 3 | 강사 신뢰 + 페르소나 분석 시스템 (5, 6) | **진행 완료** |
| Phase 4 | 문제 공감 + 통찰 + 비교 (2, 3, 4) | **진행 완료** |
| Phase 5 | 커리큘럼 + 결과물 + 1:1 비교 (7, 8, 9) | **진행 완료** |
| Phase 6 | 대상 + 가격 + FAQ + 폴리싱 (10, 11, 12) + 폼·트래킹·OG | **진행 완료** |

## 작업 규칙

- 한 번에 한 Phase만 진행. 이전 Phase 완료 체크리스트가 통과돼야 다음 Phase 시작.
- 빌드 도구·npm·추가 패키지 도입 금지. Tailwind CDN + Pretendard CDN 외 도입 시 헌법 검토.
- 판단이 흔들리면 [`docs/PROJECT.md`](docs/PROJECT.md)로 돌아간다.

## 출시 전 체크리스트

### 자산 교체
- [ ] 강사 사진 (`assets/images/instructor.jpg`) — 섹션 5 좌측 가상 박스 교체
- [ ] 결과물 스크린샷 6개 (`assets/images/result-1.png` ~ `result-6.png`) — 섹션 5 갤러리
- [ ] 페르소나 분석 시스템 스크린샷 (`assets/images/persona-system.png`) — 섹션 6 좌측
- [ ] 히어로 우측 비주얼 (`assets/images/hero-visual.png`) — 섹션 1 우측 박스
- [ ] OG 이미지 실제 이미지로 교체 (`assets/og/og-image.png`) — 현재 SVG placeholder
- [ ] favicon 실제 디자인으로 교체 (`assets/og/favicon.svg` 또는 `.ico`)

### 트래킹 코드 (`index.html` `<head>` 안 주석 해제)
- [ ] GA4 측정 ID 발급 + `G-XXXXXXXXXX` 치환
- [ ] Meta Pixel ID 발급 + `YOUR_PIXEL_ID` 치환
- [ ] Microsoft Clarity ID 발급 + `YOUR_CLARITY_ID` 치환
- [ ] 폼 제출 이벤트 주석 활성화 (`gtag('event', 'lead_submit')`, `fbq('track', 'Lead')`)

### 폼 제출
- [ ] Formspree(또는 자체 백엔드) 폼 ID 발급
- [ ] `index.html` 폼 `action` URL의 `YOUR_FORM_ID` 치환
- [ ] `thanks.html` redirect 동작 확인 (`_next` hidden 필드)

### 배포
- [ ] 도메인 결정 (`amakers.co.kr` 권장)
- [ ] Vercel 또는 GitHub Pages 연결
- [ ] DNS 설정
- [ ] HTTPS 확인
- [ ] 모바일·데스크탑 최종 점검 (375 / 768 / 1280)
