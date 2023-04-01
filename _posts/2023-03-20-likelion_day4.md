---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 4"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 4

## 2023-03-20

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  책 추천 the blocksize war
  - BlockChain transaction
  1. 발행
  2. 거래
     1. 지갑 생성
        1. 거래를 하기위해 필요한 계좌번호 지갑주소
        2. public - 공개키
           1. 개인키로부터 생성되는 계좌번호 개념
        3. Private Key - 개인키
           1. 거래하기 위해서 필요한 비밀번호 개념으로 디지털 서명
        4. Address -
     2.
  3. 검증 - 해쉬값이 같구나, 길이가 길구나, 타겟값보다 낮구나 -원래는 컴퓨팅파워가 더 많이 쏟아부어진 것이 옳은 체인이라는 것인데 a 블록의 길이는 100개, b 블록의 길이는 97개인데 97개의 컴퓨팅 파워가 더 많다면 97개가 옳은 체인이라고 검증되는 것이지만 이런 일이 잘 일어나지도 않고 다른 이유들로 이제는 긴 체인이 옳은 거래라는 것이 통용되고 있습니다.
     1. 채굴 - 컴퓨팅 파워를 사용하여(논스를 바꾸며) 문제를 푸는 과정(블록 생성)
        1. 채굴이 블록체인 시스템에 주는 의미
           1. 체인 시스템 유지
           2. 채굴자들 이득(거래 수수료, 블록 보상)
           3. 지속가능성
           4. 사용자가 일으킨 거래 완료에 기여(finalized)
        2. 거래 수수료가 0이라도 오래된 것 순으로 정렬되어 3개는 알아서 블록에 포함되게 정해져 있습니다. 다만 이렇게 되면 시스템 유지가 어렵기 때문에 지금은 수수료를 0으로 하지 못하게 설정되어 있어요.
        3. 난이도 조정 기준
           1. 비트코인 블록은 평균 10분당 1개씩 생성, 2016개의 블록 2주 기준
           2.
- 오후수업
  css보다 조금 더 발전한 scss를 사용하기 위해서 sass를 설치합니다.

  ```jsx
  npm install -g sass
  ```

  설치가 되었는지 버전으로 확인해봅니다.

  ```jsx
  sass --version
  ```

  설치를 하고 프로젝트 폴더에 input.scss 파일을 생성해서 css보다 조금 더 편하게 css를 한 파일에 모듈화해서 사용할 수 있는데요
  보통 html파일에 css 파일을 적용하려면 link를 통해서 연결해주어야 css가 적용됩니다.
  하지만 css 파일이 많아지면 계속 link를 걸어주어야 하는 불편함이 생깁니다.
  scss는 그 외에도 다양한 장점이 있는데 사용하며 알아보겠습니다.
  이전에 sass를 설치하였기 때문에 내장된 watch 옵션을 터미널 프로젝트 폴더 내부에서 사용할 수 있고

  ```jsx
  sass --watch input.scss style.css
  ```

  이 옵션을 켜두면 scss 파일을 수정하고 저장하는 순간 css 파일로 컴파일 되어 [css.map](http://css.map) 파일이 생기면서 매핑이 됩니다.
  input.scss 파일을 생성해줍니다
  간단하게 div 태그 내부의 h1,h2 등에 적용시켜볼게요.

  ```scss
  //색상을 변수에 저장합니다.
  $offBlack: #253342;
  $rosePink: #ebb8dd;
  $darkRed: #bf2c34;
  $seaGreen: #53bda5;
  $lightGray: #cbd6e2;
  $magenta: #be398d;

  div {
    h1 {
      //사용은 저장한 변수를 사용합니다.
      background-color: $offBlack;
    }

    h2 {
      background-color: $rosePink;
    }

    h3 {
      background-color: $darkRed;
    }
    h4 {
      background-color: $seaGreen;
    }
    h5 {
      background-color: $lightGray;
    }

    a {
      h6 {
        background-color: $magenta;
      }
    }
  }
  ```

  변수에 색상을 저장하고 변수를 사용하는 방법인데 규모가 커질수록 분류하는 것이 좋겠죠?
  color.scss 파일을 만들어서

  ```scss
  $offBlack: #253342;
  $rosePink: #ebb8dd;
  $darkRed: #bf2c34;
  $seaGreen: #53bda5;
  $lightGray: #cbd6e2;
  $magenta: #be398d;
  ```

  이 부분만 저장해봅시다.
  input.scss 파일의 상단에 있는 색상을 저장한 변수 부분을 지워주세요.

  ```scss
  @import "color";
  ```

  파일이 나누어져 있기 때문에 컴퓨터는 어떤 파일을 참고해야 하는지 모르기 때문에 방금 만든 color.scss 파일을 불러오는 코드 입니다.
  mixin 같은 경우 변하는 속성들을 모아놓고 적용시킬 수 있습니다.
  button.scss 파일을 만들어서 버튼 디자인을 scss로 관리해볼게요.

  ```scss
  @mixin btnStyle($color: darkgray) {
    background-color: $color;
    color: whitesmoke;
    border: 0;
    border-radius: 12px;
    padding: 12px;
  }
  ```
