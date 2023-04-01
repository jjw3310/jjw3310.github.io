---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 9"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 9

## 2023-03-28

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  [https://royalforkblog.github.io/2014/08/11/graphical-address-generator/](https://royalforkblog.github.io/2014/08/11/graphical-address-generator/)
  sha256 → base58 Encode(얘가 노출되면 개인키가 노출됨. 이유는 레인보우테이블처럼 복호화가 가능함. base58테이블 검색. 16진수가 표현할 수 있는 경우의 숫자가 적어서 표현할 수 있는 가짓수가 z까지 다 할 수 있는 base58로 변환 숫자를 문자로 변환, 어떤 숫자를 58로 계속 나누어 나머지를 나열해서 변환) [https://learnmeabitcoin.com/technical/base58](https://learnmeabitcoin.com/technical/base58) → sha256 한 개인키를 활용해 공개키 → sha256 ripe160 → base58 Encode
  새로운 핸드폰에 지갑을 옮기려면 개인키를 통해 복구하면 됩니다.
  UTXO : 사용되지 않은 출력값 Unspent Transaction Output
  지갑이 털렸다 ⇒ 지갑 안에 키가 노출이 되었다.
  락킹 언락킹
  23+5 =
  2랑 3을 더하면 5랑 같니?

# 오후수업

날씨 api를 활용한 날씨 체크 기능
[https://home.openweathermap.org/api_keys](https://home.openweathermap.org/api_keys)
여기서 회원가입 후 my api_key에서 api key를 main.js 상단에 넣고 해봅시다.
main.js

```javascript
const API_KEY = "";

navigator.geolocation.getCurrentPosition(
  (position) => {
    const lat = position.coords.latitude;
    const lon = position.coords.longitude;
    //&units=metriic api에 추가하면 섭씨로 변경됨
    const url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${API_KEY}&units=metric`;

    console.log(url);
    //api url
    fetch(url)
      .then((response) => response.json())
      .then((data) => {
        console.log(data);
        weatherTemp.innerText =
          data.name + "," + parseInt(data.main.temp) + "℃";

        weatherIcon.src = `https://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`;
      });
  },
  () => alert("Not allowed!")
);
```

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
    <div>
      <div>
        <img
          class="weatherIcon"
          src="https://openweathermap.org/img/wn/10d@2x.png"
          alt="weather"
        />
      </div>
      <div class="weatherTemp">Seoul, 22℃</div>
    </div>
    <script src="main.js"></script>
  </body>
</html>
```

리액트에 들어가기 앞서 자바스크립트를 좀 더 익혀봅시다

```jsx
const root = document.querySelector("#root");

const mainElFrist = `<div class="main">`;
const mainElLast = `</div>`;

const titleElFirst = `<div class="title">`;
const titleElLast = `</div>`;

const ulElFirst = `<ul>`;
const ulElLast = `</ul>`;

const liElFirst = `<li>`;
const liElLast = `</li>`;

const titleContent = `리액트를 잘하려면?`;
const howToMasterReact = [
  `자바스크립트를 잘해야 한다`,
  `CSS를 잘해야 한다`,
  `HTML을 잘해야 한다`,
];

const liArray = howToMasterReact.map((v, i) => {
  return `${i + 1}. ${v}`;
});

console.log(liArray);
root.innerHTML =
  mainElFrist +
  titleElFirst +
  titleContent +
  titleElLast +
  ulElFirst +
  liElFirst +
  howToMasterReact[0] +
  liElLast +
  liElFirst +
  howToMasterReact[1] +
  liElLast +
  liElFirst +
  howToMasterReact[2] +
  liElLast +
  ulElLast +
  mainElLast;
```

[https://create-react-app.dev/](https://create-react-app.dev/)<br>
프레임워크 - 도서관에 가서 책을 읽는 것 어떤 형식을 지켜줘야 합니다.<br>
라이브러리 - 도서관에서 책을 빌려오는 것
