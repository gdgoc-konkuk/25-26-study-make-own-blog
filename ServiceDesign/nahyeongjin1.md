# 서비스 기획 & 피그마 세션

---

## ☀️ 날짜

2025.10.27

## 📜 내 작업 요약

### 1. 프로젝트 개요

- **프로젝트명: NHJ.log**
- **목표: 다 Next.js 쓸 것 같으니까 굳이굳이 React Router v7 써보기**
- **핵심 가치**
  - 무채색, 미니멀한 디자인 (Pretendard 폰트)
  - 블로그: 트러블 슈팅 위주, 한글로 작성된 정보가 부족한 기술들에 대한 정리
  - 포트폴리오: 그동안 진행한 프로젝트 소개 & 내 역할(트러블 슈팅과 연결)
  - 북마크: 유용한 링크들을 저장하고 정리 (왜 저장했는지, 언제 필요한지)

### 2. 요구사항 분석

#### 사용자 요구사항

- 트러블슈팅과 기술 정리 중심의 블로그
- Notion에서 글 작성 → 자동으로 블로그 포스트 생성
- 검색 & 태그를 통한 콘텐츠 필터링
- 포트폴리오를 통한 프로젝트 소개
- 유용한 기술 문서 링크 모음 (북마크)

#### 시스템 요구사항

- SSG를 기본으로, 필요시 SSR 사용
- Notion 변경사항 감지 → 자동 빌드
- 이미지 최적화 (Sharp + R2)
- SEO 최적화
- 빠른 로딩 속도 (Lighthouse 90+ 목표)

### 3. 주요 기능 정의

#### Phase 1 (MVP)

1. **블로그 기능**
   - Notion 글 작성 → MDX 자동 변환
   - 블로그 목록 (SSG)
   - 블로그 상세 (SSG, 코드 하이라이팅)
   - 검색 기능 ([Fuse.js](https://www.fusejs.io/demo.html))
   - 태그 필터링
   - 조회수 카운트
   - 댓글
     - CRUD (작성, 수정, 삭제)
     - 대댓글
     - 본인 댓글만 수정/삭제 가능
2. **포트폴리오 기능**
   - 랜딩 페이지
   - 프로젝트 상세 페이지
3. **공통 기능**
   - Navigation (blog, portfolio, bookmarks, about)
   - About 페이지
   - 404 페이지
   - Footer
4. **인증 기능**
   - Github Oauth 2.0 로그인
   - 세션 관리 (HTTP-only 쿠키)
   - 로그인 상태 표시 (헤더에 프로필)
   - 로그아웃

#### Phase 2 (확장)

1. **북마크 기능**
   - Notion Bookmarks Database 연동
   - 북마크 목록 (태그별 필터링)
   - 북마크 상세 (URL, 설명, 사용 사례)
2. **SEO & 품질**
   - RSS feed
   - Sitemap 자동 생성
   - Open Graph 이미지
   - Lighthouse CI

#### Phase 3 (선택)

- 시리즈 기능 (연관 포스트 그룹핑)
- 인기글 위젯
- 최근 글 위젯
- 독후감 페이지 (필요시)

### 4. 기술 스택

#### 프레임워크 & 언어

- **풀스택**: React Router v7 ([Framework mode](https://reactrouter.com/start/modes#framework))
- **언어**: Typescript
- **빌드**: Vite

#### 프론트엔드

- **스타일링**: [Tailwind CSS](https://tailwindcss.com/docs/installation/using-vite), [@tailwindcss/typography](https://www.npmjs.com/package/@tailwindcss/typography)
- **타입 검증**: [Zod](https://www.npmjs.com/package/zod)
- **검색**: [Fuse.js](https://www.fusejs.io/) (클라이언트 사이드)
- **폰트**: [Pretendard](https://github.com/orioncactus/pretendard)

#### 백엔드 & 데이터

- **CMS**: Notion (글 작성)
- **Notion 연동**: [@notionhq/client](https://www.npmjs.com/package/@notionhq/client), [notion-to-md](https://github.com/souvikinator/notion-to-md)
- **데이터베이스**: [Netlify DB](https://docs.netlify.com/build/data-and-storage/netlify-db/) (PostgreSQL)
- **ORM**: [Prisma](https://www.prisma.io/docs/guides/react-router-7)
- **인증**: Github OAuth 2.0
- **세션**: HTTP-only 쿠키 (signed)
- **보안**: DOMPurify (XSS 방지), CSRF 토큰
- **이미지**: Cloudflare R2, Sharp (최적화)

#### 배포 & CI/CD

- **호스팅**: Netlify
- **빌드**: Github Actions (Netlify free tier 빌드 제한 회피)
- **도메인**: hyeongjin.me (Github Student Pack)
- **CDN**: Cloudflare (Proxy + Bot Protection)

#### 개발 도구

- **품질**: ESLint, Prettier, Husky, lint-staged
- **커밋**: @commitlint/config-conventional
- **테스트**: Vitest
- **성능**: Lighthouse CI

### 부록

#### 공식 문서

- [[React Router v7 Docs]](https://reactrouter.com/start/modes#framework)
- [[Notion API Reference]](https://developers.notion.com/)
- [[Prisma React Router Guide]](https://www.prisma.io/docs/guides/react-router-7)
- [[Cloudflare R2 Docs]](https://developers.cloudflare.com/r2/)
- [[GitHub OAuth Apps]](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps)
- [[Netlify DB Docs]](https://docs.netlify.com/build/data-and-storage/netlify-db/)
- [[Lighthouse CI]](https://github.com/GoogleChrome/lighthouse-ci)

#### 라이브러리

- [[@notionhq/client]](https://www.npmjs.com/package/@notionhq/client)
- [[notion-to-md]](https://github.com/souvikinator/notion-to-md)
- [[DOMPurify]](https://www.npmjs.com/package/isomorphic-dompurify)
- [[Fuse.js]](https://www.fusejs.io/)
- [[Pretendard Font]](https://github.com/orioncactus/pretendard)

## 📜 내 작업 내용 중 가장 인상깊었던 부분 & 가장 배움이 컸던 부분

1. 최대한 표준에서 벗어나지 않으면서 차별점을 찾다보니 풀스택 프레임워크 중 React Router 선택
2. 화면을 그리드로 구성할 때 열 개수가 어느정도 표준화되어있다는 것을 알게 됨
3. 디자인 경험이 없어 피그마 세션에서의 개념 정리가 도움 됨

## 📜 이수경님 작업 내용 중 인상깊었던 부분

- **프레임**, 그룹, 모양
- 오토 레이아웃, 정렬, 제약 조건
- 스타일 가이드
- 참고 링크
  - [반응형 웹 그리드 시스템 계산기](https://designbase.co.kr/grid-calculator/)
  - [Color Generator](https://kigen.design/color)

## 📜 이율원님 작업 내용 중 인상깊었던 부분

이전에 개발했던 블로그를 보여주며 기획안 발표를 진행했고
전체적인 디자인과 효과들이 인상적이었다.
특히 그레이스케일의 깔끔한 디자인을 추구하는 나의 방향성과 비슷한 부분이 있어
일정 부분 참고하는 것도 좋을 것 같다.

## 📜 정지원님 작업 내용 중 인상깊었던 부분

레퍼런스들 나도 참고하기 좋을 것 같은 느낌
