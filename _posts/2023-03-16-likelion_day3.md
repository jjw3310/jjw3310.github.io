---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 3"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 3

## 2023-03-17

<style>
  .content {
    font-size : 18px;
  }
</style>

## 오전수업

블록체인은 탈중앙화된 네트워크에서 작동하는 분산원장 기술
발행 : 규칙성 있게 하자→ 거래 : 지갑을 만들자→ 검증 : 아무나 들어올 수 있는데 일정 규칙(채굴)이란 과정을 만들자
블록구조에서 어떤 것이 채굴과 관련이 있지?
리먼 브라더스 → 탈중앙화 → 비트코인

1. 익명성 - 전화번호만 보고 누군지 알 수 없는 것처럼 주소만 보고 누군지 알 수 없어요
2. 추적가능성 - 모든 거래가 기록 됩니다. 누가 USDC를 사고 누가 파는지 보고 같이 따라들어가는 투자기법이 유행하기도 했어요.
   익명성과 추적가능성이 상대되는 개념이기 때문에 혹자들은 익명성이 아니라 준익명성이라고 하기도 합니다.
3. 무신뢰성 - 누군가에게 돈을 송금할 경우 누군가를 믿고(은행, 카카오, 정부 등) 거래를 하는데 블록체인에서는 신뢰 받는 제 3기관은 존재하지 않고 거래하는 상대방도 믿지 않아도 되며 시스템 자체가 신뢰를 담보합니다.
4. 분산원장 - 시스템 내 모든 참가자들은 거래의 정보를 기록하고 있습니다. 소문 퍼져나가는 것처럼 다른 사람에게 거래정보를 보내고 받은 사람은 또 보내는 과정을 거칩니다.
5. 탈중앙화 - 전통적인 시스템과 달리 블록체인에는 중앙화된 주체가 존재하지 않습니다.
6. 합의 알고리즘 - 동등한 권한의 다수가 참여하기 때문에, 옳은 정보(해쉬값 비교)를 결정하는 규칙이 필요합니다.
7. 변경 불가능성 - 한 번 블록체인에 정보가 들어가면 쉽게 바뀌지 않습니다. 변경이 불가능하진 않지만 각 블록에는 이전 블록값을 담고있는데 변경이 되었을 경우 블록해쉬값이 변경되기 때문에 변경을 빠르게 알아챌 수 있습니다.
   채굴은 무작위 숫자가 들어가는 것이 아니라 블록에 대한 정보들이 같이 들어가서 값을 찾는 것
   [https://www.blockchain.com/explorer/blocks/btc?page=1](https://www.blockchain.com/explorer/blocks/btc?page=1)
   비트코인의 블록정보를 볼 수 있는 서비스
   [https://emn178.github.io/online-tools/sha256.html](https://emn178.github.io/online-tools/sha256.html)
   SHA256 사이트

- 제네시스 블록(코인베이스)
  - 거래에는 송신자와 수신자가 있는데 송신자가 없고 수신자만 있을 경우 채굴 보상을 지급합니다.
    채굴자는 블록에 거래를 1개라도 더 많이 채울수록 채굴보상을 많이 받을 수 있습니다.
    하지만 예를 들어서 누군가 악의적인 목적으로 빈 블록만 계속 만드는 것도 피해를 끼칠 목적으로라면 가능하기도 합니다.
    머클루트 - 블록의 거래 정보를 기반으로 만들어집니다.
    블록 헤더에는 Hash, version, previous Hash, Merkle Root, Time, Bits & Difficulty, Nonce가 있는데 bits를 통해서 현재 찾아야하는 값이 뭔지 알 수 있습니다.
    SHA256 - 64자리, 256bit
    1, 7, 10
    10은 단독으로 만들어지지 않고
    1과 0을 합쳐서 만들어집니다.
    자릿수를 올려서 표현해주어야 하죠.
    ‘
    채굴과정
    결과값으로 나오는 해시값은 2진수 기준으로 256자리 16진수 기준으로 64자리
    블록에서 변화하는 값은 논스값과 해쉬값 밖에 없음.
    변화시키는 것은 논스값이고 그에 따라 변화하는 것이 해쉬값이기 때문에
    공정한 검증을 하기 위해서 타겟값이라는 기준 값을 정해놓고
    논스를 통해 나온 해쉬값이 타겟값보다 낮으면 채굴 성공을 규칙으로 하자
    타겟값이 낮으면 난이도가 높다!
    50개 → 반감기 → 25개 → … → 6.25개

# 오후수업

css 속성값 중 grid에 대해서 배워봅시다!
먼저 html 파일을 만든 후 css파일을 만들어서 적용시킵니다.

```jsx
//index.html
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
    <div class="container">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```

```css
//style.css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px 200px;
  grid-template-rows: 100px 200px 50px 200px 100px;
  gap: 20px;
  background-color: aqua;
}

.box {
  background-color: pink;
}
```

gap에 색을 입히고 싶은 경우
.container 클래스에 background-color: aqua; 를 입력합니다.
보통 grid는 화면을 분할하고 싶은 경우 사용하는데
비율에 맞추어 분할하고 싶은 경우 repeat 함수를 활용해서 적용합니다.
`grid-template-columns: repeat(4, 1fr);`
grid로 레이아웃 잡아봅시다!

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
    <div class="container">
      <div class="header"></div>
      <div class="nav"></div>
      <div class="content"></div>
      <div class="footer"></div>
    </div>
  </body>
</html>
```

```css
//style.css
body {
  margin: 0;
}

.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 100px auto 100px;
  height: 100vh;
}

.header {
  background-color: aquamarine;
  grid-column: 1/ 5;
  grid-row: 1/2;
}

.nav {
  background-color: blueviolet;
  grid-column: 1/ 2;
  grid-row: 2/3;
}

.content {
  background-color: coral;
  grid-column: 2/ 5;
  grid-row: 2/3;
}

.footer {
  background-color: gold;
  grid-column: 1/ 5;
  grid-row: 3/4;
}
```
