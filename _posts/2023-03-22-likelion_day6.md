---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 6"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 6

## 2023-03-22

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  합의 알고리즘을 거쳐서 옳은 블록으로 판단 된 블록이 되면 옳지 않은 블록으로 판단 된 블록은
  0 → a : 10
  b → c : 2
  c → a : 4
  d → a : 3
  0 → a : 10
  c → d : 2
  d → h : 3
  b → a : 2
  암호학
  - 단방향성
    - 암호화 복호화가 불가
  - 양방향성
    - 암호화 복호화가 가능
  1. 키쌍 생성
  2. 평문 넣기
  3. 공개키 복붙해서 암호화하기
  4. 암호화
  5. 암호문 확인
  6. 암호문 복붙
  7. 개인키 복붙해서 복호화하기
  8. 복호화
  9. 평문 확인
- 오후수업

  - javascript 문자열 더하기 및 조건문

  ```jsx
  const BLOCK = "블";
  const BBLE = "쁠";
  const CHAIN = "체";
  const SCHOOL = "스";

  const rightWord = BLOCK + CHAIN + SCHOOL;

  if (rightWord === "블체스") {
    console.log("블체스 화이팅!");
  }
  ```

  ```jsx
  const 나는프로그래머다 = true;
  const 나는천개의비트코인이있다 = false;
  const 내가제일좋아하는음료는제로콜라다 = true;

  // 나머지 변수도 사용해보세요.
  let trueOrFalse = 나는프로그래머다;

  if (trueOrFalse) {
    console.log("당신은 거짓을 말하지 않는 선량한 사람입니다 😇");
  } else {
    console.log("당신은 거짓말쟁이에 나쁜 사람입니다 🤬");
  }
  ```

  for문

  ```jsx
  for (let i = 0; i < 10; i++) {
    if (i === 0) {
      console.log("우리는?");
    } else if (i % 3 === 0) {
      console.log(`${i} 스`);
    } else if (i % 2 === 0) {
      console.log(i + " 체");
    } else {
      console.log(i + " 블");
    }
  }
  ```

  javascript 타이머 만들기 main.js파일

  ```jsx
  function getTime() {
    const time = document.querySelector(".time");

    const newDate = new Date();

    const hours = String(newDate.getHours()).padStart(2, "0");
    const minutes = String(newDate.getMinutes()).padStart(2, "0");
    const seconds = String(newDate.getSeconds()).padStart(2, "0");

    // time.innerText = hours + ":" + minutes + ":" + seconds;
    time.innerText = `${hours}:${minutes}:${seconds}`;
  }

  //   getTime();
  setInterval(getTime, 1000);
  ```

  html 파일 내부에 넣어주어 스크립트를 참조합니다.

  ```html
  <script src="main.js"></script>
  ```

  디자인을 이쁘게 꾸미려면 input.scss를 적용합니다.

  ```bash
  sass --watch input.scss style.css
  ```

  sass 명령어로 input.scss 파일을 저장하면 style.css에 적용되게 실행시킨 후 input.scss를 수정합니다.

  ```css
  body {
    margin: 0;
    color: rgb(22, 22, 22);
  }

  .bgVideo {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    object-fit: cover;
  }

  main {
    position: fixed;
    z-index: 2;
    width: 100vw;
    height: 100vh;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  ```
