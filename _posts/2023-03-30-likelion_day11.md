---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 11 part2"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 11

## 2023-03-30

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  Tailwind CSS는 UI 프레임워크가 아닌 유틸리티 클래스를 통해 스타일링을 할 수 있는 CSS 라이브러리입니다. Tailwind CSS를 사용하는 방법에 대해서 알아보겠습니다.

  1. 먼저 Tailwind CSS를 사용하기 위해서는 npm을 통해 설치해야 합니다. 설치 명령어는 다음과 같습니다.

  ```jsx
  npm install tailwindcss

  ```

  2.  Tailwind CSS를 사용하기 위해서는 설정 파일을 생성해야 합니다. 설정 파일을 생성하는 명령어는 다음과 같습니다.

  ```jsx
  npx tailwindcss init

  ```

  3.  생성된 설정 파일을 수정하여 원하는 스타일을 적용할 수 있습니다. 기본 스타일을 설정할 때는 extend 객체 안에 스타일을 추가해주면 됩니다. 예를 들어, 다음과 같이 색상을 추가할 수 있습니다.

  ```javascript
  module.exports = {
    content: ["./src//*.{js,jsx,ts,tsx}"],
    theme: {
      extend: {
        colors: {
          "my-green": "#00FF00",
        },
      },
    },
    variants: {},
    plugins: [],
  };
  ```

  4.  HTML에서 Tailwind CSS를 사용하기 위해서는 클래스명을 입력하는 것만으로 스타일링을 할 수 있습니다. 예를 들어, 다음과 같이 버튼의 스타일을 적용할 수 있습니다.

  ```html
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
  >
    Button
  </button>
  ```

  5.  만일 반복되는 스타일이 있을 경우 유틸리티 클래스를 추가로 만들어서 사용할 수 있습니다. 예를 들어, 다음과 같이 버튼과 사이드바 메뉴의 스타일을 추가로 만들어서 사용할 수 있습니다.

  ```javascript
  module.exports = {
    theme: {
      extend: {
        colors: {
          "my-green": "#00FF00",
        },
        spacing: {
          72: "18rem",
        },
      },
    },
    variants: {},
    plugins: [
      function ({ addUtilities }) {
        const newUtilities = {
          ".btn": {
            padding: ".5rem 1rem",
            borderRadius: ".25rem",
            fontWeight: "600",
          },
          ".btn-blue": {
            backgroundColor: "#3490dc",
            color: "#fff",
            "&:hover": {
              backgroundColor: "#2779bd",
            },
          },
          ".sidebar": {
            backgroundColor: "#f7fafc",
            borderColor: "#edf2f7",
            borderWidth: "1px",
          },
        };
        addUtilities(newUtilities);
      },
    ],
  };
  ```

  6.  자식 태그 순서에 따른 스타일 설정도 쉽게 할 수 있습니다. 자식 태그 클래스에 hover:와 같이 last: 프리픽스를 사용합니다. 예를 들어, 다음과 같이 메뉴를 스타일링할 수 있습니다.

  ```html
  <ul class="list-none">
    <li class="last:mr-0 hover:text-gray-800">
      <a href="#">Menu 1</a>
    </li>
    <li class="last:mr-0 hover:text-gray-800">
      <a href="#">Menu 2</a>
    </li>
    <li class="last:mr-0 hover:text-gray-800">
      <a href="#">Menu 3</a>
    </li>
  </ul>
  ```

  7.  tailwind를 components 방식으로 관리할 수 있습니다. index.css 파일을 만들어서 사용하면 됩니다.

  ```css
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  @layer components {
    .btn-style {
      @apply px-2 py-1 rounded-md text-gray-100 cursor-pointer;
    }
  }
  ```

  Tailwind CSS를 사용하는 방법에 대해서 알아보았습니다. Tailwind CSS는 UI 프레임워크가 아니기 때문에 UI 단위가 아닌 유틸리티 클래스를 사용하여 스타일링을 할 수 있습니다. 이를 통해 작성해야 하는 코드의 양을 줄이고, 한번 작성한 코드를 재사용할 수 있습니다. 그러나 유틸리티 클래스를 사용하면서 CSS 파일의 크기가 커지는 문제가 있기 때문에 적절한 커스터마이징과 최적화가 필요합니다.
