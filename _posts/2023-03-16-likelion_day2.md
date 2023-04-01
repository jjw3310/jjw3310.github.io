---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 2"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 2

## 2023-03-16

<style>
  .content {
    font-size : 18px;
  }
</style>

[https://rdi.berkeley.edu/berkeley-defi/f22](https://rdi.berkeley.edu/berkeley-defi/f22)

금리를 통해 통화량의 완급조절을 하는데 금리를 올렸다 내렸다 통화를 늘렸다 줄였다 하면 시장이 불안정하니 일정하게 통화를 발행해서 하겠다! 그게 비트코인이다

탈중앙화 된 시장에서 은행 같은 중앙기관이 없기 때문에 거래가 없어지면 안되니까 개인의 계좌는 있어야 합니다.

그럼 누군가에게 돈을 보냈을 때 이 거래를 어떻게 신뢰할 수 있을까요?

중앙기관이 없는 peer to peer 거래의 경우 어떻게 거래를 신뢰할 수 있도록 검증을 할까에 대한 고민이 필요합니다.

그래서 이 거래를 모든 사람에게 알려주면 조금은 신뢰도가 올라갑니다.

그리고 일정시간마다 거래를 한 곳에 기록하여 모든 사람의 거래장부를 업데이트하면 훨씬 더 신뢰할 수 있는 거래가 됩니다.

이 개념으로 인해 블록체인은 분산 거래 원장 이라는 개념이 성립되었습니다.

권한을 증명하는 것은 누구에게나 해주었지만

데이터를 모아서 검증할 사람에게 클린하게 시스템을 유지하기 위해서

문제를 풀게해서 이 데이터를 검증할 수 있는 권한을 주자

모든 사람에게 어려운 문제를 주자

모든 사람에게 균등하게 문제를 주기위해 sha256이라는 규칙성이 없어서 예측하기 불가능한 함수를 사용해서 이 조건을 먼저 맞춘 사람에게 권한을 주자

그런데 누가 이 어려운 문제를 풀어?

문제를 푼 사람에게 보상을 주자!

채굴자는 시스템에서 설정한 블록생성 보상과 거래수수료를 보상으로 받습니다.

2-1 비트코인백서

- 비트코인을 시작한이유, 목적, 특징 그리고 구성 요소에 대한 설명이 요약되어 있는 문서
- [https://github.com/bitcoinbook/bitcoinbook](https://github.com/bitcoinbook/bitcoinbook)

2-2 마스터링 비트코인

- 비트코인에 대한 기술적인 세부적인 내용들이 매우 정확하게 설명되어 있는 책, 컴퓨터공학, 암호학에 대한 기본적인 지식이 없다면 이해하기 쉽지 않음. 하지만 이 책만 100% 이해하면 비트코인의 기본 원리에 대해서 거의 완벽하게 이해했다고 볼 수 있음.

1 왜 달러는 비트코인을 싫어하는가? - bitcoin standard

3 사토시의 서

- 사토시가 해왔던 언급들을 모아놓아 사토시의 입김을 간접적으로 느낄 수 있는 책. 어떤 생각으로 설계했고 발전시키려고 했는지 배울 수 있음. 어떠한 고민을 하는지 왜 하는지에 대해서 그 사고의 흐름을 따라가보면서 알아보면 더욱 깊게 이해할 수 있음

4 프로그래밍 비트코인

- 비트코인을 하나씩 직접 코딩으로 만들어보는 과정을 알려주는 책, 기본적으로 비트코인에 대한 이해가 높은 상태에서 읽어야 의미가 있음. 코딩을 기본적으로 할 줄 알아야 함.

인벤팅 비트코인

비탈릭 부테린 지분증명

- 합의알고리즘의 아쉬움들을 채워가면서구현해보고 싶다.

<br>

# 오후 수업

## 이미지 svg 불러오기

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <img src="techit_logo.svg" alt="logo" />
  </body>
</html>
```

extension - Live Server

- 다운로드 받아서 vscode 하단에 golive 버튼 클릭하면 5500번 포트가 열리며 브라우저가 열리고 코드를 수정하고 저장하는 순간 바로 수정화면을 볼 수 있습니다. 서버를 종료할 땐 다시 golive 클릭하면 됩니다.
  button을 추가하려면 <button> 태그를 사용합니다.

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
    <img src="techit_logo.svg" alt="logo" />
    <button>테킷 스쿨</button>
    <button>스타트업 스테이션</button>
    <button>VOD 클래스</button>
    <button>기업교육</button>
    <button>이벤트</button>
    <button>로그인</button>
  </body>
</html>
```

테킷의 헤더를 만들어 보고 css 속성 중 헷갈리는 것 3개를 같은 크기로 설정했을 때 어떻게 변하는지 비교해봅시다.

- inline-block
  - 한 줄 안에 블록의 형태로 적용
- block
  - 블록의 형태로 한 줄을 차지
- inline
  - 한 줄 안에 영역 크기 변경이 불가

```
//style.css
.ib {
  display: inline-block;
  background-color: blue;
  width: 150px;
  height: 150px;
}
.b {
  display: block;
  background-color: red;
  width: 150px;
  height: 150px;
}
.i {
  display: inline;
  background-color: gray;
  width: 150px;
  height: 150px;
}
```

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
    <header>
      <div class="menu">
        <img src="techit_logo.svg" alt="logo" />
        <button class="firstBtn">테킷 스쿨</button>
        <button>스타트업 스테이션</button>
        <button>VOD 클래스</button>
        <button>기업교육</button>
        <button>이벤트</button>
      </div>
      <div class="loginBox">
        <button class="login">로그인</button>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          class="ellipsis"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          ></path>
        </svg>
      </div>
    </header>
    <div>
      <div class="ib">인라인 블록</div>
      <div class="ib">인라인 블록</div>
      <div class="ib">인라인 블록</div>
    </div>
    <div>
      <div class="b">블록</div>
      <div class="b">블록</div>
      <div class="b">블록</div>
    </div>
    <div>
      <div class="i">인라인</div>
      <div class="i">인라인</div>
      <div class="i">인라인</div>
    </div>
  </body>
</html>
```
