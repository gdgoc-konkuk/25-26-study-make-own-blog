### 날짜
2025.10.27

### 📜 내 작업 요약

## **1. 프로젝트 개요**

- **프로젝트명**: zzig.log / Studio Zziglet / zziglet.view
- **목표**: 기술 블로그와 개인 포트폴리오를 한 곳에서 관리할 수 있는 통합 웹사이트 제작
- **핵심 가치**:
    - 블로그: 학습 기록 및 기술 공유
    - 포트폴리오: 프로젝트/성과 정리 및 외부 공유

---

## **2. 요구사항 분석**

### **사용자 요구사항**

- 상단 탭에서 **Blog / Portfolio** 쉽게 이동 가능
- 블로그 글 작성 및 관리 → Notion 연동으로 자동 반영
- 포트폴리오 → 프로젝트별 상세 페이지(이미지, 설명, 사용 기술, GitHub 링크 포함)
- 모바일/데스크탑 반응형 지원
- 검색 및 카테고리(태그) 분류 기능

### **시스템 요구사항**

- SSR 기반 SEO 최적화 (구글 검색 노출)
- Lighthouse 점수 93점 이상 달성
- PostgreSQL에 사용자 메타데이터 및 포트폴리오 관리

---

## **3. 주요 기능 정의**

1. **블로그 기능**
    - Notion API 기반 글 동기화
    - 카테고리, 태그 기반 글 목록 제공
    - 검색 기능 지원
    - Github 로그인 및 댓글 기능
2. **포트폴리오 기능**
    - 프로젝트 카드 형태로 전시 (썸네일 + 짧은 설명)
    - 클릭 시 상세 페이지 이동 (기술 스택, 역할, GitHub/배포 링크 포함)
    - 필터링(프로젝트 유형, 사용 기술 등)
3. **공통 기능**
    - 상단 네비게이션 바 (Blog / Portfolio / About)
    - 성능 최적화 (이미지 최적화, 캐싱, CDN)

---

## **4. 기술 스택**

- **Frontend/Backend**: Next.js (App Router 기반)
- **CSS** : @emotion/styled
- **Database**: PostgreSQL
- **DB 호스팅** : Supabase
- **ORM**: Prisma
- **CMS 역할**: Notion API 연동
- **OAuth**
    - **Giscus**(GitHub Discussions 기반)나 **utterances**(GitHub Issues 기반)를 사용하는 것을 강력히 추천합니다. 개발 2차 일정이 훨씬 가벼워질 것입니다.
- **Hosting/Deployment**: Vercel (프론트/백엔드 포함)
- **Analytics/성능 측정**: Google Analytics, Lighthouse
- **버전 관리**: GitHub

### 📜 내 작업 내용 중 가장 인상깊었던 부분 & 가장 배움이 컸던 부분

- 드디어 나만의 블로그 내용을 기획할 수 있다는 점이 가장 인상 깊었다.
- Next 풀스택으로 개발하기 위한 기술 스택들을 찾아보면서 1인 개발자를 위한 다양한 기술이 존재한다는 것을 알았다.

### 📜 이율원 님 작업 내용 중 인상깊었던 부분

https://sterd.dev

율원님 블로그 짱짱맨 참고해보기

### 📜 나형진 님 작업 내용 중 인상깊었던 부분

형진님의 notion 계획 훔쳐오기
**Notion 연동**: [@notionhq/client](https://www.npmjs.com/package/@notionhq/client), [notion-to-md](https://github.com/souvikinator/notion-to-md)

git student domain 무료 찾아보기

### 📜 이수경 님 피그마 세션 중 인상깊었던 부분

1. font 규칙 배우기
2. frame vs. group
    - frame : 변형 O
    - group  변형 X
3. 단축키 : cmd option []
    
    ⇒ layer 뒤바꾸기
    
4. auto layout 반응형
    
5. top 
    
6. color style
    - 500으로 main값 잡고
    - plugin 활용하기
7. font style
    - 주어진 웹 font에 따라서 넣기