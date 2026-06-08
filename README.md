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
| Phase 3 | 강사 신뢰 + 페르소나 분석 시스템 (5, 6) | 예정 |
| Phase 4 | 문제 공감 + 통찰 + 비교 (2, 3, 4) | 예정 |
| Phase 5 | 커리큘럼 + 결과물 + 1:1 비교 (7, 8, 9) | 예정 |
| Phase 6 | 대상 + 가격 + FAQ + 폴리싱 (10, 11, 12) + 폼·트래킹·OG | 예정 |

## 작업 규칙

- 한 번에 한 Phase만 진행. 이전 Phase 완료 체크리스트가 통과돼야 다음 Phase 시작.
- 빌드 도구·npm·추가 패키지 도입 금지. Tailwind CDN + Pretendard CDN 외 도입 시 헌법 검토.
- 판단이 흔들리면 [`docs/PROJECT.md`](docs/PROJECT.md)로 돌아간다.
