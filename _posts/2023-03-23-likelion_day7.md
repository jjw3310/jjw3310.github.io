---
layout: post
title: "멋쟁이사자처럼 블록체인 스쿨 day 7"
tags: 멋쟁이사자처럼 블록체인스쿨 블록체인 개발자 블록체인 blockchain
---

# 멋쟁이사자처럼 블록체인 스쿨 day 7

## 2023-03-23

<style>
  .content {
    font-size : 18px;
  }
</style>

- 오전수업
  암호화, 복호화
  원본의 내용을 일련의 과정을 통해서 가리는 행위를 암호화, 가려진 결과물을 다시 원본으로 돌리는 과정을 복호화라 합니다.
  단방향성, 양방향성
  암호화와 복호화가 진행 가능한 방향에 따라 결정되는데 암호화만 가능하지만 복호화는 불가능한 비트코인 공개키 및 주소 생성의 경우에는 단방향성 입니다. 양방향성은 암호화와 복호화가 모두 가능한 상태
  비트코인과 타원곡선 (Bitcoin and Eilliptic Curve
  비트코인에서 사용되는 타원곡선 즉, secp256k1의 식은 a=0이고 b=7인 ?!@#!@#

  1. [https://www.devglan.com/online-tools/rsa-encryption-decryption](https://www.devglan.com/online-tools/rsa-encryption-decryption)
  2. [https://encode-decode.com/des-encrypt-online/](https://encode-decode.com/des-encrypt-online/)

  3. 지갑-개인키 준비

  4. RSA(비대칭키 방식)에서 pub-pvt key pair 생성
  5. pub ke로 지갑-개인키 암호화
  6. 암호문 복붙
  7. pvt-key 복붙
  8. des에서 개인 비밀번호로 암호화
  9. 6번에서 생성된 암호문 복붙

     private key 안전하게 보관하기 위해서

- 오후수업
  1. 배열을 만든다
  2. let b = JSON.stringify(a); 문자열화 한다.
  3. let c = JSON.parse(b); 파싱한다.

3기 수강생 분들께 알려드릴 지식!

    git log --oneline  //로그를 한 줄로 커밋메세지와 함께 간단하게 볼 수 있는 명령어
    git reset --hard <커밋번호> // 기록이 남지 않게 해당 커밋으로 돌아가고 그 이후 기록은 모두 사라집니다. *신중히 사용
    git revert <커밋번호> //돌아가고 싶은 커밋도 하나의 추가적인 커밋으로 생성하는 명령어 입니다.
    git reflog // 지워진 커밋들의 정보도 볼 수 있습니다.
    git reset --hard HEAD@{0} // git reset --hard 로 날려버렸을 경우 이전 커밋으로 돌립니다. 안되는 경우도 있으니 reset --hard는 조심히 사용하시길 바래요!
