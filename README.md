# Minimal Portfolio - Next.js + Supabase

## 🔗 빠른 링크
- 📑 기획서(피그마 슬라이드): https://www.figma.com/file/XXXX
- 🎨 디자인 원본(피그마): https://www.figma.com/file/YYYY

---

## 1. 프로젝트 개요

### 1.1 목표
- **포트폴리오 전시**: 개인 작업물을 한 곳에 모아 소개
- **실서비스 구현**: Next.js App Router + Supabase 기반의 인증, 데이터 관리, 파일 업로드
- **관리 효율성**: 관리자 전용 CRUD 기능
- **배포 경험**: Vercel 기반 CI/CD

### 1.2 팀원

| 이름 | 역할 | 주요 담당 | GitHub |
| --- | --- | --- | --- |
| 김동주 | 팀장 · FE 리드 | 아키텍처/폴더링, CI/CD, Supabase 스키마, 성능 최적화 | [@alikerock](https://github.com/alikerock) |
| 이가람 | FE | 포트폴리오 페이지, 검색·필터, 상태관리, 접근성 개선 | [@garam-dev](https://github.com/garam-dev) |
| 박지우 | FE · 디자인 | 디자인 시스템, 반응형 레이아웃, 이미지 업로드/최적화 | [@jiwoo-park](https://github.com/jiwoo-park) |

---

## 2. 마일스톤

1. **기획/설계**: 요구사항·화면흐름, 데이터 모델, 기본 라우팅
2. **핵심 기능**: 목록/상세, 이미지 업로드, 관리자 Auth + CRUD
3. **품질/운영**: SEO, 성능 최적화, 접근성 점검
4. **테스트/배포**: E2E 테스트, GitHub Actions, 문서화

---

## 3. 주요 기능

- **Auth**: 이메일 로그인, 관리자 전용 권한 제어(RLS)
- **프로젝트 관리**: 등록/수정/삭제, 이미지 업로드(Storage)
- **UI/UX**: 검색·필터, 페이지네이션, 반응형 레이아웃
- **SEO**: OG 태그, sitemap, robots

---

## 4. 기술 스택

### Frontend
- **Framework**: Next.js 15.x (App Router)
- **Styling**: Tailwind CSS, CSS Modules
- **State Management**: SWR / React Query
- **Image Handling**: next/image

### Backend (BaaS)
- **Database**: Supabase(PostgreSQL)
- **Auth**: Supabase Auth
- **Storage**: Supabase Storage

### Tools
- **Version Control**: Git & GitHub
- **Deployment**: Vercel
- **Design**: Figma

---

## 5. 라우팅 구조

| 경로 | 설명 | 접근 권한 |
|------|------|-----------|
| `/` | 메인 홈(프로젝트 목록) | 전체 |
| `/portfolio` | 포트폴리오 전체 보기 | 전체 |
| `/portfolio/[id]` | 프로젝트 상세 | 전체 |
| `/about` | 자기소개 | 전체 |
| `/contact` | 연락 페이지 | 전체 |
| `/admin/login` | 관리자 로그인 | 비로그인 |
| `/admin/dashboard` | 대시보드 | 관리자 |
| `/admin/insert` | 프로젝트 등록 | 관리자 |
| `/admin/edit/[id]` | 프로젝트 수정 | 관리자 |

---

## 6. 실행 방법

```bash
# 1. 클론
git clone https://github.com/alikerock/portfolio-nextjs_supabase.git
cd portfolio-nextjs_supabase

# 2. 패키지 설치
npm install

# 3. 환경변수 설정
cp .env.example .env.local

# 4. 로컬 실행
npm run dev

# 5. 프로덕션 빌드
npm run build
npm start
```

---

## 7. 향후 개선 사항
- 프로젝트 검색/필터링 UI 강화
- 이미지 썸네일 자동 생성
- Contact 폼 → 메일 발송
- E2E 테스트 및 배포 자동화
- Lighthouse 성능/SEO 90점 이상 달성
