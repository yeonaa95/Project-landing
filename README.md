# 개인 프로젝트 실습 / Project-landing

> 첫번째 프로젝트 실습 2 - 랜딩 페이지 ZADU <br>
> https://yeonaa95.github.io/Project-landing/

---

# 🎨 반응형 랜딩 페이지 제작 프로젝트 가이드

## 📋 프로젝트 개요

이 프로젝트는 **모바일 우선(Mobile First)** 방식의 반응형 랜딩 페이지를 처음부터 제작하는 실습입니다.

제공된 이미지 리소스를 활용하여 `index.html`과 `styles.css`를 직접 작성하고, 다양한 화면 크기에서 적절하게 표시되는 웹 페이지를 완성해보세요.

### 🎨 디자인 파일

전체 디자인은 Figma에서 확인할 수 있습니다:

**[📐 Figma 디자인 보기](https://www.figma.com/design/86GxsHTa7nXPKM8S15WOVw/EST_SECURITY_FE_%E1%84%80%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%B2?node-id=49-1791&t=cyWpVReMat7JAvCo-1)**

> **💡 팁**: Figma에서 디자인을 확인하면 정확한 색상, 폰트 크기, 여백 등을 쉽게 파악할 수 있습니다!

---

## 🎯 학습 목표

- ✅ HTML5 시맨틱 태그를 활용한 구조적인 마크업
- ✅ CSS 변수(Custom Properties)를 이용한 일관된 디자인 시스템
- ✅ Flexbox를 활용한 레이아웃 구성
- ✅ 모바일 우선(Mobile First) 반응형 디자인
- ✅ 미디어 쿼리를 활용한 다양한 화면 대응
- ✅ JavaScript를 이용한 기본적인 인터랙션 구현

---

## 📁 프로젝트 구조

```
landing/
├── images/          # 이미지 리소스 (제공됨)
│   ├── logo_h.png
│   ├── box-cat.png
│   ├── cat-subscribe.png
│   ├── up-cat.png
│   ├── img_1.jpg
│   ├── img_2.jpg
│   ├── img_3.jpg
│   ├── img_4.jpg
│   └── mail.svg
├── index.html       # 여러분이 작성할 파일
├── styles.css       # 여러분이 작성할 파일
└── README.md        # 이 파일
```

---

## 🎨 디자인 요구사항

### 색상 팔레트

프로젝트에서 사용할 주요 색상입니다. CSS 변수로 정의하여 사용하세요.

```css
:root {
  /* 기본 색상 */
  --primary-color: #f8b49b; /* 연한 살구색 */
  --accent-color: #ef835d; /* 강조색 (버튼, 아이콘) */
  --accent-hover: #dc5b28; /* 호버 상태 색상 */
  --header-bg-color: #f2d8d9; /* 헤더/히어로 배경색 */
  --dark-bg: #2c3e50; /* 다크 배경 (구독 섹션) */

  /* 텍스트 색상 */
  --text-color: #333; /* 기본 텍스트 */
  --text-light: #666; /* 밝은 텍스트 */
  --text-lighter: #f2e9d8; /* 더 밝은 텍스트 */

  /* 기타 */
  --border-color: #eee; /* 테두리 색상 */

  /* 그림자 효과 */
  --shadow-sm: 0 2px 5px rgba(0, 0, 0, 0.1);
  --shadow-md: 0 4px 8px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 4px 15px rgba(0, 0, 0, 0.1);
}
```

> **💡 팁**: CSS 변수를 활용하면 색상이나 그림자 효과를 한 곳에서 쉽게 관리할 수 있습니다!

### 폰트

- 기본 폰트: `Arial, sans-serif`
- 기본 텍스트 색상: `#333`

---

## 📱 반응형 디자인 가이드

### 모바일 우선(Mobile First) 접근

1. **기본 스타일 (768px 이하)**: 모바일 화면을 기준으로 먼저 작성
2. **미디어 쿼리 (768px 이상)**: 태블릿 및 데스크톱 화면 대응

### 주요 브레이크포인트

```css
/* 모바일: 기본 스타일 (768px 이하) */
/* 태블릿/데스크톱: @media (min-width: 768px) */
```

---

## 🏗️ 페이지 구조

페이지는 다음 5개의 주요 섹션으로 구성됩니다:

### 1. 📌 Header (헤더)

- 왼쪽: ZADU 로고 (`images/logo_h.png`)
- 오른쪽 (데스크톱): 네비게이션 메뉴 (Home, About, Support) + Download 버튼
- 오른쪽 (모바일): 햄버거 메뉴 버튼 (☰)
- 배경색: `--header-bg-color`

**구현 팁:**

- 모바일에서는 네비게이션을 `display: none`으로 숨기고, 햄버거 버튼만 표시
- 768px 이상에서는 네비게이션을 `display: flex`로 표시하고, 햄버거 버튼 숨김

---

### 2. 🦸 Hero Section (히어로 섹션)

- 왼쪽: 텍스트 콘텐츠 (제목, 설명, Download 버튼)
- 오른쪽: 고양이 이미지 (`images/box-cat.png`)
- 배경색: `--header-bg-color`

**레이아웃:**

- 모바일: 세로 배치 (`flex-direction: column`)
- 데스크톱: 가로 배치 (`flex-direction: row`, 각 50%)

**텍스트 내용:**

```
제목: Lorem ipsum is simply dummy text of the printing and
설명: Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the 1500s.
      when an unknown
```

---

### 3. 📸 Card Section (카드 섹션)

- 왼쪽: 이미지 (`images/img_4.jpg`)
- 오른쪽: 텍스트 콘텐츠

**레이아웃:**

- 모바일: 세로 배치 (이미지 위, 텍스트 아래)
- 데스크톱: 가로 배치 (이미지 왼쪽, 텍스트 오른쪽, 각 50%)

**스타일링:**

- 이미지에 그림자 효과: `box-shadow: var(--shadow-md)` 또는 `box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1)`
- 이미지 모서리 둥글게: `border-radius: 8px`

---

### 4. 🖼️ Gallery Section (갤러리 섹션)

3개의 서브 섹션으로 구성:

#### a) 중앙 텍스트

- 제목 (주황색): "dummy text of the printing and dummy"
- 설명

#### b) 이미지 갤러리

- 3개의 이미지를 가로로 배치 (`images/img_1.jpg`, `img_2.jpg`, `img_3.jpg`)
- 이미지 스타일: `border-radius: 15px`, 그림자 효과

#### c) 하단 컨테이너

- 텍스트 설명 (왼쪽)
- "Learn More" 버튼 (오른쪽)

**레이아웃:**

- 모바일: 갤러리 이미지가 세로로 쌓임
- 데스크톱: 갤러리 이미지가 가로로 3개 (각 30% 너비)

---

### 5. 📧 Subscribe Section (구독 섹션)

- 다크 배경 (`--dark-bg`)에 흰색 텍스트
- 왼쪽: "Subscribe to our Blog post" 제목 및 설명
- 오른쪽: 이메일 입력 폼 + Subscribe 버튼
- 배경 이미지: `images/up-cat.png` (::after 가상 요소 사용)

**레이아웃:**

- 모바일: 세로 배치 (텍스트 위, 폼 아래)
- 데스크톱: 가로 배치 (텍스트 왼쪽, 폼 오른쪽)

**입력 폼 구성:**

- 메일 아이콘 (`images/mail.svg`) + 이메일 입력 필드 + Subscribe 버튼
- 흰색 배경, 둥근 모서리

**중요 구현 사항:**

- `position: relative`로 섹션 위치 지정
- `::after` 가상 요소로 배경 이미지 (`images/up-cat.png`) 추가
- `z-index: -1`로 배경 뒤로 보내기

---

### 6. 🔗 Footer (푸터)

- 상단:
  - 왼쪽: 로고
  - 오른쪽: SNS 아이콘 (4개 - 블로그, 인스타그램, 페이스북, 유튜브)
- 하단 (데스크톱에서는 숨김):
  - About, Blog, Support, Term of Use 링크

**SNS 아이콘 스타일:**

- 원형 배경 (`border-radius: 50%`)
- 배경색: `--accent-color`
- 아이콘 색상: 흰색

**레이아웃:**

- 모바일: 상단(로고 + SNS)와 하단(링크) 세로 배치
- 데스크톱: 로고와 SNS만 가로로 배치 (하단 링크 숨김)

---

### 7. 🎭 Modal (모달)

Subscribe 버튼 클릭 시 나타나는 감사 메시지 모달:

- 반투명한 검은색 오버레이 (`rgba(0, 0, 0, 0.6)`)
- 중앙 정렬된 모달 박스
- 내용:
  - 고양이 이미지 (`images/cat-subscribe.png`)
  - "Thank you!" 메시지
  - 설명 텍스트
  - "OK! I Love ZADU" 버튼
- 닫기 버튼 (X) - 우측 상단

**구현 팁:**

- `position: fixed`로 전체 화면 오버레이
- `.hidden` 클래스로 초기에는 숨김 (`display: none`)
- JavaScript로 버튼 클릭 시 `.hidden` 클래스 토글

---

## 💻 JavaScript 기능

### 모달 제어

Subscribe 버튼 클릭 시 모달을 표시하고, 다음 방법으로 닫을 수 있어야 합니다:

1. 닫기 버튼 (X) 클릭
2. 오버레이 배경 클릭

```javascript
// 필요한 요소 선택
const modal = document.getElementById("my-modal");
const subscribeBtn = document.getElementById("subscribe-btn");
const closeBtn = document.querySelector(".modal-close-btn");

// 1. Subscribe 버튼 클릭 시 모달 표시
subscribeBtn.addEventListener("click", function (event) {
  event.preventDefault(); // 폼 제출 방지
  modal.classList.remove("hidden");
});

// 2. 닫기 버튼 클릭 시 모달 숨김
closeBtn.addEventListener("click", function () {
  modal.classList.add("hidden");
});

// 3. 오버레이 클릭 시 모달 숨김
modal.addEventListener("click", function (event) {
  if (event.target === modal) {
    modal.classList.add("hidden");
  }
});
```

---

## 🎯 구현 단계별 가이드

### Phase 1: HTML 구조 작성

1. **기본 HTML 구조 생성**

   ```html
   <!DOCTYPE html>
   <html lang="ko">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>ZADU - 반응형 레이아웃</title>
       <link rel="stylesheet" href="styles.css" />
     </head>
     <body>
       <div class="container">
         <!-- 여기에 섹션들을 추가 -->
       </div>
     </body>
   </html>
   ```

2. **시맨틱 태그 사용하기**

   - `<header>`: 헤더 섹션
   - `<nav>`: 네비게이션 메뉴
   - `<section>`: 각 콘텐츠 섹션
   - `<footer>`: 푸터 섹션

3. **각 섹션별 HTML 작성**
   - Header → Hero → Card → Gallery → Subscribe → Footer → Modal 순서로 작성

---

### Phase 2: CSS 기본 스타일 (모바일)

1. **CSS 변수 정의**

   ```css
   :root {
     --primary-color: #f8b49b;
     --accent-color: #ef835d;
     /* ... */
   }
   ```

2. **전역 스타일 설정**

   ```css
   * {
     box-sizing: border-box; /* 박스 모델 일관성 */
   }

   body {
     margin: 0;
     font-family: Arial, sans-serif;
     color: var(--text-color);
     line-height: 1.6;
   }

   img {
     max-width: 100%; /* 이미지 반응형 기본 설정 */
     height: auto;
   }
   ```

3. **모바일 우선으로 각 섹션 스타일링**
   - 모바일에서는 대부분 `flex-direction: column` 사용
   - 작은 화면에 맞는 폰트 크기, 여백 설정

---

### Phase 3: 반응형 디자인 (데스크톱)

1. **미디어 쿼리 추가**

   ```css
   @media (min-width: 768px) {
     /* 태블릿/데스크톱 스타일 */
   }
   ```

2. **레이아웃 변경**

   - `flex-direction: row`로 변경
   - 너비 50% 분할 (hero, card 섹션)
   - 네비게이션 메뉴 표시, 햄버거 버튼 숨김

3. **폰트 크기 및 여백 조정**
   - 더 큰 화면에 맞게 제목 크기 증가
   - 여백(padding, gap) 확대

---

### Phase 4: JavaScript 인터랙션

1. **모달 기능 구현**

   - Subscribe 버튼 클릭 이벤트
   - 모달 닫기 이벤트
   - 오버레이 클릭 이벤트

2. **테스트**
   - 모든 인터랙션이 정상 작동하는지 확인

---

## 📐 주요 CSS 기법

### CSS 변수 활용

일관된 디자인을 위해 CSS 변수를 적극 활용하세요:

```css
.action-btn {
  background-color: var(--accent-color);
  transition: background-color 0.3s ease;
}

.action-btn:hover {
  background-color: var(--accent-hover);
}

.image-left {
  box-shadow: var(--shadow-md);
}
```

### Flexbox 활용

대부분의 레이아웃은 Flexbox를 사용합니다:

```css
.hero-section {
  display: flex;
  flex-direction: column; /* 모바일 */
}

@media (min-width: 768px) {
  .hero-section {
    flex-direction: row; /* 데스크톱 */
  }
}
```

### 가상 요소 (::after)

Subscribe 섹션의 배경 이미지:

```css
.subscribe-section::after {
  content: "";
  position: absolute;
  background: url("images/up-cat.png") no-repeat center bottom;
  background-size: contain;
  z-index: -1;
}
```

### SVG 아이콘 스타일링

```css
.social-icon {
  background-color: var(--accent-color);
  border-radius: 50%;
  transition: background-color 0.3s ease;
}

.social-icon:hover {
  background-color: var(--accent-hover);
}

.social-icon svg {
  width: 24px;
  height: 24px;
  color: white;
}
```

### Transition 효과

부드러운 사용자 경험을 위해 transition을 추가하세요:

```css
.action-btn,
.social-icon,
.footer-bottom a,
.main-nav a {
  transition: all 0.3s ease;
}
```

---

## 🌟 추가 도전 과제

기본 구현을 완료했다면, 다음 기능들을 추가해보세요:

1. **햄버거 메뉴 기능**

   - 모바일에서 햄버거 버튼 클릭 시 네비게이션 메뉴가 나타나도록 구현

2. **스크롤 애니메이션**

   - 섹션이 화면에 나타날 때 fade-in 효과 추가

3. **이메일 유효성 검사**

   - Subscribe 폼에서 올바른 이메일 형식인지 검증

4. **이미지 Lazy Loading**

   - 갤러리 이미지에 `loading="lazy"` 속성 추가

5. **접근성 개선**
   - ARIA 속성 추가
   - 키보드 네비게이션 지원

---

## 📝 체크리스트

구현이 완료되었는지 확인하세요:

### HTML

- [ ] 모든 섹션이 올바른 순서로 배치됨
- [ ] 시맨틱 태그를 적절히 사용함
- [ ] 모든 이미지에 `alt` 속성이 있음
- [ ] 모달 구조가 올바르게 작성됨

### CSS

- [ ] CSS 변수를 정의하고 사용함
- [ ] 모바일 우선으로 스타일을 작성함
- [ ] `@media (min-width: 768px)` 미디어 쿼리를 사용함
- [ ] Flexbox를 활용한 레이아웃
- [ ] 모든 버튼과 링크에 hover 효과가 있음 (transition 사용)

### 반응형

- [ ] 모바일(~767px)에서 정상 표시됨
- [ ] 태블릿/데스크톱(768px~)에서 정상 표시됨
- [ ] 헤더의 네비게이션이 화면 크기에 따라 적절히 표시/숨김됨
- [ ] 모든 섹션의 레이아웃이 반응형으로 변경됨

### JavaScript

- [ ] Subscribe 버튼 클릭 시 모달이 표시됨
- [ ] 닫기 버튼 클릭 시 모달이 닫힘
- [ ] 오버레이 클릭 시 모달이 닫힘
- [ ] 폼 제출이 방지됨 (`event.preventDefault()`)

---

## 🎓 학습 참고 자료

### CSS

- [MDN - Flexbox](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Flexible_Box_Layout)
- [MDN - Media Queries](https://developer.mozilla.org/ko/docs/Web/CSS/Media_Queries)
- [MDN - CSS Variables](https://developer.mozilla.org/ko/docs/Web/CSS/Using_CSS_custom_properties)

### JavaScript

- [MDN - addEventListener](https://developer.mozilla.org/ko/docs/Web/API/EventTarget/addEventListener)
- [MDN - classList](https://developer.mozilla.org/ko/docs/Web/API/Element/classList)
- [MDN - Event.preventDefault](https://developer.mozilla.org/ko/docs/Web/API/Event/preventDefault)

---

## 💡 구현 팁

### 1. 단계별로 진행하기

- 한 번에 모든 것을 구현하려 하지 말고, 섹션별로 나누어 진행하세요.
- HTML → CSS (모바일) → CSS (데스크톱) → JavaScript 순서를 추천합니다.

### 2. 브라우저 개발자 도구 활용

- `F12` 또는 `Cmd+Option+I` (Mac)로 개발자 도구를 열어보세요.
- 반응형 디자인 모드 (`Cmd+Shift+M` 또는 `Ctrl+Shift+M`)로 다양한 화면 크기를 테스트하세요.

### 3. 자주 테스트하기

- 코드를 작성할 때마다 브라우저에서 결과를 확인하세요.
- 모바일과 데스크톱 두 가지 화면 크기에서 모두 테스트하세요.

### 4. 주석 활용하기

- CSS에 섹션별로 주석을 추가하여 코드를 구조화하세요.

```css
/* ========================================================= */
/* Header */
/* ========================================================= */
```

### 5. 문제 해결

- 막히는 부분이 있다면:
  1. 브라우저 개발자 도구의 Elements 탭에서 스타일을 확인
  2. CSS 속성이 예상대로 적용되고 있는지 체크
  3. Flexbox 레이아웃의 경우 `flex-direction`, `justify-content`, `align-items` 확인

---

## 🚀 시작하기

1. `index.html` 파일을 생성하고 기본 HTML 구조를 작성하세요.
2. `styles.css` 파일을 생성하고 CSS 변수부터 정의하세요.
3. 한 섹션씩 차근차근 구현해나가세요.
4. 완성 후 다양한 화면 크기에서 테스트해보세요!

---

## ✨ 마무리

이 프로젝트를 통해 다음을 배우게 됩니다:

- 실무에서 사용하는 **모바일 우선 반응형 디자인** 방법론
- **Flexbox**를 활용한 현대적인 레이아웃 구성
- **CSS 변수**를 통한 유지보수 가능한 스타일 시스템
- **미디어 쿼리**를 사용한 다양한 디바이스 대응
- **JavaScript**를 이용한 기본적인 UI 인터랙션

**화이팅! 🎉**
