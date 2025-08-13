# Nestlé Website Renewal
> HTML/CSS/JS 정적 웹사이트 리뉴얼 프로젝트

## 목차
- [프로젝트 개요](#프로젝트-개요)
- [폴더 구조](#폴더-구조)
- [주요 기능](#주요-기능)
- [페이지 맵](#페이지-맵)
- [빠른 시작](#빠른-시작)
- [개발 가이드](#개발-가이드)
- [빌드 & 배포](#빌드--배포)
- [브라우저 지원](#브라우저-지원)
- [품질 체크리스트](#품질-체크리스트)
- [크레딧](#크레딧)

---

## 프로젝트 개요
Nestlé 브랜드 웹사이트를 **정적 페이지(HTML/CSS/JS)** 로 리뉴얼한 프로젝트입니다. 브랜드 스토리 전달력과 제품 가독성을 높이기 위해 **간결한 레이아웃, 대조가 뚜렷한 타이포, 대형 히어로 이미지/영상**을 활용했습니다.  
디렉터리 구성은 `index.html` 과 `css/`, `js/`, `images/`, `video/` 로 나뉘며, 간단한 스크립트로 내비게이션, 슬라이더 등 인터랙션을 제공합니다.

- **주요 기술**: HTML5, CSS3, JavaScript(ES6)
- **디자인 목표**: 브랜드 아이덴티티 반영, 접근성(명도 대비/키보드 내비게이션), 반응형 레이아웃
- **성과 지표 예시**: LCP 2.5s 이내, CLS 0.1 이하, Lighthouse 90+ (Performance/Accessibility/SEO)

---

## 폴더 구조
```
/ (repo root)
├─ index.html          # 진입점
├─ css/                # 스타일 시트 (reset, layout, components 등)
├─ js/                 # 스크립트 (nav, carousel, modal 등)
├─ images/             # 이미지 자산 (logo, 제품, 배너)
└─ video/              # 히어로/배경 영상 등
```
> 실제 리포지토리 내에는 `index.html`, `css/`, `js/`, `images/`, `video/` 폴더가 포함되어 있습니다.

---

## 주요 기능
- **헤더/내비게이션**: 스티키 헤더, 모바일 메뉴 토글
- **히어로 섹션**: 대형 이미지/동영상 배경, 핵심 메시지
- **제품 소개**: 카드 레이아웃, 호버 인터랙션, 간단한 필터/탭
- **스토리/ESG 섹션**: 브랜드 가치 및 지속가능성 소개
- **푸터**: 약관/개인정보/소셜 링크
- **접근성 배려**: 시맨틱 마크업, 스킵 링크, 대체 텍스트, 명도 대비
- **반응형**: 모바일 퍼스트, 주요 브레이크포인트(375/768/1200px)

---

## 페이지 맵
- `/index.html` – 메인 랜딩  
  - Hero, 제품 하이라이트, 브랜드 스토리, 뉴스/프로모션, CTA

필요 시, 아래와 같이 확장 가능합니다.
- `/products.html` – 제품 목록/필터
- `/about.html` – 브랜드 스토리
- `/sustainability.html` – ESG/CSV 활동
- `/contact.html` – 문의/고객센터

---

## 빠른 시작
로컬에서 바로 열람하거나, VS Code **Live Server** 확장으로 개발합니다.

### 1) 의존성 없음 (정적 프로젝트)
```bash
# 클론
git clone https://github.com/likerang/Renewal_project_Nestle.git
cd Renewal_project_Nestle

# 바로 열기
# macOS
open index.html

# Windows
start index.html
```

### 2) VS Code Live Server (권장)
1. VS Code에서 폴더 열기
2. 확장 탭에서 **Live Server** 설치
3. `index.html` 우클릭 → **Open with Live Server**

---

## 개발 가이드
### CSS
- `css/`를 역할별로 분리: `base.css`(reset/variables) → `layout.css` → `components.css`(버튼, 카드, 모달)
- 가능한 경우 **CSS 변수**(`:root`)로 컬러/타이포 스케일 관리
- 이미지/영상 위 텍스트 대비 확보(최소 WCAG AA)

### JavaScript
- DOMContentLoaded 이후 초기화: `initNav()`, `initCarousel()`, `initModal()` 등
- 외부 라이브러리 없이 순수 JS로 토글/슬라이더 구현(필요 시 경량 라이브러리 도입 가능)
- 스크립트는 **지연 로딩**(`defer`)으로 렌더 블로킹 최소화

### 자산(Images/Video)
- WebP/AVIF 우선, 폴백 제공
- `width/height` 명시로 **CLS 방지**
- 영상은 짧고 용량 최적화(무음 자동재생 시 `muted playsinline`)

---

## 빌드 & 배포
정적 사이트이므로 **정적 호스팅**을 사용합니다.

- **GitHub Pages**  
  - Settings → Pages → Branch 선택 → 저장  
  - 기본 도메인: `https://<username>.github.io/Renewal_project_Nestle/`
- **Vercel / Netlify**  
  - 새 프로젝트로 연결 → 루트 디렉토리 선택 → 배포  
  - 빌드 스텝 불필요(Framework 미사용)

---

## 브라우저 지원
- 최신 Chromium/Firefox/Safari/Edge
- IE 미지원(필요 시 CSS/JS 폴리필 전략 수립)

---

## 품질 체크리스트
- [ ] Lighthouse Performance/Accessibility/SEO/Best Practices 90+
- [ ] 키보드만으로 주요 내비게이션 가능
- [ ] 이미지 대체 텍스트 제공
- [ ] 모바일 375px 기준에서 주요 컴포넌트 깨짐 없음
- [ ] 메타 태그(og:, twitter:) 및 favicon 세팅
- [ ] 폴더/파일 네이밍 컨벤션 준수 (kebab-case)

---

## 크레딧
- 디자인/기획: Team Nestlé Renewal
- 개발: HTML/CSS/JS Contributors
- 라이선스: 본 저장소 내 이미지/영상의 사용 범위는 Nestlé 브랜드 가이드에 따릅니다.

---

## Learn More
- HTML: https://developer.mozilla.org/docs/Web/HTML
- CSS: https://developer.mozilla.org/docs/Web/CSS
- JS: https://developer.mozilla.org/docs/Web/JavaScript
- 접근성: https://www.w3.org/WAI/standards-guidelines/wcag/
