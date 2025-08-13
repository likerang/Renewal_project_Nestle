# CSS 컨벤션 가이드

## 1. CSS 변수 (Custom Properties)
* **`:root`**에 전역 변수 정의
* **kebab-case** 네이밍 사용
* 색상, 폰트, 레이아웃 기본값 관리

```css
:root{
  --container: 1200px;
  --fz: 16px;
  --lh: 24px;
  --black: rgba(33, 33, 33, 1);
  --primary: rgba(254, 90, 21, 1);
}
```

## 2. 타이포그래피 시스템
* **계층적 폰트 크기** 정의 (`main-tt`, `section-tt36`, `card-title`)
* **calc() 함수**로 반응형 크기 계산
* **font 단축 속성** 적극 활용

```css
.main-tt{
  font: calc(var(--lh) * 2);
  font-size: calc(var(--fz) * 3);
  font-weight: bold;
}
```

## 3. 컴포넌트 기반 버튼
* **크기별 버튼** 클래스 (`btn_large`, `btn_medium`, `btn_small`)
* **공통 스타일** 먼저 정의 후 개별 스타일 적용
* **일관된 호버/액티브** 상태 처리

```css
.btn_large, .btn_medium, .btn_small{
  border: 1px solid var(--black);
  background: #fff;
  transition: 0.3s;
}
```

## 4. 네이밍 규칙
* **snake_case** 주로 사용 (`btn_large`, `section-tt36`)
* **의미 기반 네이밍** (크기: large/medium/small, 용도: main/section/card)
* **BEM 유사 패턴** 일부 적용

## 5. 색상 관리
* **RGBA 색상값** 사용으로 투명도 조절 가능
* **시멘틱 네이밍** (`--primary`, `--brandcolor`)
* **그레이스케일** 단계별 정의

## 6. 레이아웃
* **CSS 변수**로 컨테이너 너비 관리
* **중앙 정렬** 패턴 일관성 유지
* **calc() 함수** 활용한 동적 계산

```css
.container{
  width: var(--container);
  margin: 0 auto;
}
```