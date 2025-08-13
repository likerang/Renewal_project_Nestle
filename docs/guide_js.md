# JavaScript 컨벤션 가이드

## 1. 네이밍 규칙
- **변수/함수**: `camelCase` (예: `currentSlideIndex`, `moveSlide()`)
- **상수**: `SCREAMING_SNAKE_CASE` (예: `SLIDE_DURATION`)
- **의미있는 이름** 사용 (`idx` → `currentIndex`)

## 2. 코드 구조
```javascript
// ========================================
// 기능별 섹션 구분
// ========================================

// 관련 변수들 그룹화
const slideConfig = {
  width: 320,
  duration: 4000,
  gap: 50
};

// 함수화로 재사용성 높이기
function initSlider() { }
function handleEvents() { }
```

## 3. 이벤트 처리
```javascript
// 명시적 함수 사용
button.addEventListener('click', handleButtonClick);

function handleButtonClick(event) {
  event.preventDefault();
  // 로직 구현
}
```

## 4. 에러 처리 및 검증
```javascript
function moveSlide(index) {
  if (!slides || slides.length === 0) return;
  if (index < 0 || index >= slides.length) return;
  
  // 슬라이드 이동 로직
}
```

## 5. 주요 개선 포인트
- **함수 분리**: 긴 코드를 작은 함수들로 나누기
- **전역 변수 최소화**: 네임스페이스나 모듈 패턴 사용
- **매직 넘버 제거**: 의미있는 상수로 대체
- **일관된 스타일**: 들여쓰기, 세미콜론, 따옴표 통일

## 6. 권장 파일 구조
```javascript
// 1. 상수 선언
// 2. 전역 변수
// 3. 유틸리티 함수들  
// 4. 메인 기능 함수들
// 5. 이벤트 리스너 등록
// 6. 초기화 실행
```