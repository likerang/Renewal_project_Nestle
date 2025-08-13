# HTML 컨벤션 가이드

## 1. 문서 구조
* **HTML5** DOCTYPE 선언 필수
* `lang` 속성 명시 (다국어 지원)
* **시맨틱 태그** 적극 활용 (`<header>`, `<section>`, `<nav>`, `<footer>`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

## 2. 들여쓰기와 포맷팅
* 들여쓰기는 **스페이스 2칸**
* 태그는 **소문자** 사용
* 속성값은 **큰따옴표("")** 사용

```html
<section class="main_slide">
  <div class="mainslide-wrapper">
    <ul>
      <li class="m_slide1 active">
```

## 3. 클래스 네이밍
* **snake_case** 또는 **kebab-case** 혼용
* BEM 방식 일부 적용 (`main-tt`, `section-tt28`)
* 의미있는 클래스명 사용 (`news_bigtitle`, `sliderwrapper`)

## 4. 이미지 및 접근성
* **alt 속성** 필수 (한국어로 명확한 설명)
* 의미있는 파일명 사용
* SVG 아이콘 적극 활용

```html
<img src="images/company_img1.png" alt="좋은 식품, 건강한 삶">
```

## 5. 폼과 상호작용
* **id**와 **for** 속성으로 레이블 연결
* **button** 태그에 `type` 속성 명시
* **form** 요소에 `action` 속성 설정

```html
<input type="checkbox" id="check">
<label for="check">오늘 하루 안보기</label>
<button type="button" class="prev">
```

## 6. 주석
* 섹션별 시작/종료 주석 사용
* 담당자별 구분 주석 활용

```html
<!-- 헤더영역 ws -->
<header>
  <!-- 내용 -->
</header>
<!-- //헤더영역 -->
```