### 날짜
2025.10.27

### 📜 내 작업 요약

#### 1. 프로젝트 개요

- **프로젝트명**: sterdlog
- **목표**: https://sterd.dev 마이그레이션 ⇒ 개인 이력서 및 포트폴리오, 기술 블로그, TIL(Today I Learned)을 한 사이트에서 보여주기
- **핵심 가치**:
    - 이력서 및 포트폴리오: 진행했던 개인 또는 팀 프로젝트 정보를 체계적으로 관리
    - 블로그: 학습 기록 관리(대부분 TIL에서 적은 조각들을 합치는 방향으로 생성)
    - TIL: 오늘 하루에 배운 내용 또는 읽은 자료들 간략 정리

#### 2. 요구사항 분석

##### **사용자 요구사항**

- https://sterd.dev 페이지의 모든 기능 이관
- 상단 Navigation에서 각 페이지 이동(fixed)
- 블로그 글 작성 및 관리(MDX)
    - Obsidian Vault → Next.js Pipeline 구축
    - Obsidian Vault에 Git Plugin 깔아서 자동 커밋/푸시
- 포트폴리오 → 프로젝트별 상세 페이지(이미지, 설명, 사용 기술, GitHub 링크 포함)
- 모바일/데스크탑 반응형 지원
- 검색 및 카테고리(태그) 분류 기능

##### **시스템 요구사항**

- Gatsby + styled-component → Next.js + tailwindcss Migratino
- SSR 기반 SEO 최적화 (구글 검색 노출)
- Lighthouse 점수 90점 이상 달성
- 다크모드 및 일관된 UI/UX 제공

#### 3. 주요 기능 정의

1. **블로그 기능**
    - Obsidian Vault 연동
    - 카테고리 별 filter 기능 지원
    - 검색 기능 지원
2. TIL
    - Obsidian Vault 연동
    - 검색 기능 지원
3. **포트폴리오 기능**
    - 프로젝트 카드 형태로 전시 (썸네일 + 짧은 설명 + stack chips)
    - 클릭 시 상세 페이지 이동 (기술 스택, 역할, GitHub/배포 링크 포함)
    - 필터링(프로젝트 유형, 사용 기술 등)
4. **공통 기능**
    - 상단 네비게이션 바 (Main, Portfolio, Blog, TIL)
    - 다크모드 지원
    - 성능 최적화 (이미지 최적화, 캐싱, CDN)

#### 4. 기술 스택

- **Frontend/Backend**: Next.js (App Router 기반)
- **CMS 역할**: Obsidian Vault + Obsidian Git
- **Hosting/Deployment**: Vercel
- **Analytics/성능 측정**: Google Analytics, Lighthouse
- **버전 관리**: GitHub

#### 5. 시스템 아키텍처

```
[사용자]
   ↓
[Next.js 프론트엔드]
   ├── Portfolio 페이지 (Static)
   ├── Blog 페이지 (Obsidian Vault에서 가져온 내용)
   └── TIL 페이지 (Obsidian Vault에서 가져온 내용)
   ↑
[Obsidian Vault] (Obsidian Git으로 수정 내용 자동 Commit/Push)
```

#### 6. 일정 계획

- **개발 1차**
    - vercel 배포 및 프로젝트 세팅
    - CI/CD 환경 세팅
    - 프론트 포트폴리오 화면
- **개발 2차**
    - 프론트 블로그 화면
    - Obsidian 연동

#### 7. 예상 비용

- 도메인: 이미 사용 중인 도메인 그대로 사용
- DNS: Cloudflare DNS

#### 8. 레퍼런스 & 예시 컨셉

- **컨셉 방향**:
    - Primary Color: #2563e1
    - Glassmorphism?
    - 전반적으로 깔끔하고 정돈된 UI

#### 9. 필요한 지식 & 학습 내용

- **Next.js (App Router)**: SSR/SSG, API Routes, SEO
- **배포**: Vercel
- **CI/CD**: Obsidian Push 시 Github Action을 통해 Vercel Deploy Hook 호출
- **Git/GitHub**: 브랜치 전략, PR 리뷰

#### 10. 프로젝트 관리 & 컨벤션

- **형상 관리 전략**: Git Flow (main / develop / feature)
- **Git Commit 컨벤션 (Conventional Commit)**
    - feat: 새로운 기능 추가
    - fix: 버그 수정
    - docs: 문서 수정
    - style: 코드 포맷팅 (비즈니스 로직 변경 없음)
    - refactor: 리팩토링
    - chore: 빌드/패키지 관리 변경
- **작업 방식**:
    1. 이슈 생성 → 브랜치 생성(feature/#이슈번호-작업내용)
    2. PR 생성 & 코드 리뷰
    3. develop에 머지
    4. 버전 관리를 통해 main에 release PR로 머지 예정

### 📜 내 작업 내용 중 가장 인상깊었던 부분 & 가장 배움이 컸던 부분

- 방치되고있던 블로그를 살려보자.. 이번엔 제대로 써보고싶음..
- 피그마를 제대로 강의를 들어본 적은 처음인데, 체계적으로 배워보니 느낌이 색달랐다.
- 기회가 된다면 좀 더 길게 들어보고 싶다.. 피그마 스터디 개설해주세용..

### 📜 다른 스터디원 작업 내용 중 인상깊었던 부분
- Notion API 쓰는 사람이 생각보다 많음.. 나도 노션을 좀 써봐야 하나..
- 테크 기업 기술 블로그들도 좀 참고해보기!