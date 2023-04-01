---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 5"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 5

## 2023-03-21

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  합의 알고리즘
  - POW : 합의 알고리즘이 나온 이유는 불특정 다수가 옳은 권한을 결정할 방법이 없어서 합의 알고리즘. 다수결, 제일 빨리 올린 사람 등의 방법들보다 누가 들어도 불만이 나오지 않을만한 방법이 없을까하다 나온 모두에게 어렵지만 검증은 쉬운 합의 알고리즘
    [비트코인 코어 github](https://github.com/bitcoin/bitcoin)
    c++ 로 만들어진 비트코인 코어를 현재는 rust, js 등의 다른 언어도 만들어야 한다는 논의가 진행되고 있습니다.
    [https://blog.lopp.net/who-controls-bitcoin-core-/](https://blog.lopp.net/who-controls-bitcoin-core-/)
    sha256의 특징
  - 인풋값이 다르면 아웃풋 값이 다르다
  - 인풋값에 상관없이 용량은 무조건 같다.
  - 16진수 64자리, 2진수로 표현하자면 256자리
  - 결국 sha256 결과값도 숫자
    nonce 값을 변경하면 머클 해쉬에 영향을 미치고 머클 해쉬는 블록 해쉬에 영향을 미침.
    주변에 있는 노드들과 블록을 비교하는 여러 조건들이 있는데 시간, 버전, 난이도를 비교하는 구조로 받을지 말지 결정합니다. 그리고 bits값을 누군가 임의로 변경할 수 없게 제약조건들이 걸려있습니다.
    bits 값을 수식을 통해 변경하여 난이도를 구할 수 있습니다.
- 오후수업
  일단 오늘은 scss로 반응형 웹을 만드는 과정을 진행해볼게요. index.html 파일과 input.scss를 만들어줍니다. 그리고 다른 파일인 responsive.scss에 정의하여 input.scss에서 사용하는 방법을 익혀봅시다.
  index.html

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" content="IE=edge" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Document</title>
      <link rel="stylesheet" href="style.css" />
    </head>
    <body>
      <h1>Hello, SCSS!</h1>
    </body>
  </html>
  ```

  responsive.scss

  ```scss
  $tablet: 768px;
  $laptop: 1024px;
  $pc: 1280px;

  @mixin responsive($device) {
    @if $device == "tablet" {
      @media (min-width: $tablet) {
        @content;
      }
    } @else if $device == "laptop" {
      @media (min-width: $laptop) {
        @content;
      }
    } @else if $device == "pc" {
      @media (min-width: $pc) {
        @content;
      }
    }
  }
  ```

  input.scss

  ```scss
  @import "responsive";

  body {
    margin: 0;
    background-color: lightpink;
    @include responsive("tablet") {
      background-color: pink;
    }

    @include responsive("laptop") {
      background-color: hotpink;
    }

    @include responsive("pc") {
      background-color: deeppink;
    }
  }
  ```

  js의 특징

  - 변수 var, let, const 차이
  - node 브러우저 외부 실행
  - 변수의 자료형 Array 및 object

  ```jsx
  const hello = ["hello", "hi", "don't forget this."];

  const chains = [
    { name: "mainnet", chainId: 1 },
    { name: "polygon", chainId: 137 },
    { name: "avalanche", chainId: 43114 },
    { name: "arbitrum", chainId: 42161 },
    { name: "gnosis", chainId: 100 },
    { name: "bsc", chainId: 56 },
    { name: "optimism", chainId: 10 },
    { name: "fantom", chainId: 250 },
  ];

  console.log(chains);
  console.log(chains[0]);

  // 여전히 const 임에도 불구하고 접근이 가능한 문제가 남아있습니다.
  // chains[0].name = "hackednet";
  // console.log(chains[0]);
  ```
