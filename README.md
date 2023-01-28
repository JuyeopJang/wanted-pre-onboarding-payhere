# 페이히어 기업 과제

## 과제 소개
고객이 본인의 소비내역을 기록, 관리할 수 있는 가계부 기능을 구현하는 과제

## 요구 사항
- 1. 고객은 이메일과 비밀번호 입력을 통해서 회원 가입을 할 수 있습니다.
- 2. 고객은 회원 가입 이후, 로그인과 로그아웃을 할 수 있습니다.
- 3. 고객은 로그인 이후 가계부 관련 아래의 행동을 할 수 있습니다.
    - a. 가계부에 오늘 사용한 돈의 금액과 관련된 메모를 남길 수 있습니다.
    - b. 가계부에서 수정을 원하는 내역은 금액과 메모를 수정할 수 있습니다.
    - c. 가계부에서 삭제를 원하는 내역은 삭제할 수 있습니다.
    - d. 삭제한 내역은 언제든지 다시 복구할 수 있어야 합니다.
    - e. 가계부에서 이제까지 기록한 가계부 리스트를 볼 수 있습니다.
    - f. 가계부에서 상세한 세부 내역을 볼 수 있습니다.
- 4. 로그인하지 않은 고객은 가계부 내역에 대한 접근 제한 처리가 되어야 합니다.

## 담당 역할 및 요구 사항 분석
- 유저 모듈 제작 및 테스트
    - 1. 고객은 이메일과 비밀번호 입력을 통해서 회원 가입을 할 수 있습니다.
        - 유저는 이메일과 비밀번호 속성을 가진다.
        - 중복 회원 가입은 할 수 없다.
        - 보안을 위해 [비밀번호를 해싱](https://velog.io/@zooyeop/%EC%9B%90%ED%8B%B0%EB%93%9C-%ED%94%84%EB%A6%AC%EC%98%A8%EB%B3%B4%EB%94%A9-%EB%B0%B1%EC%97%94%EB%93%9C-%EC%BD%94%EC%8A%A4-2%EC%A3%BC%EC%B0%A8-%ED%9B%84%EA%B8%B0)해서 저장한다.
        - 비밀번호는 문자, 숫자, 특수문자를 최소 한 개 포함하며 최소 8글자에서 최대 16글자이다.
    - 2. 고객은 회원 가입 이후, 로그인과 로그아웃을 할 수 있습니다.
        - 이미 회원 가입된 유저만 로그인 할 수 있다.
        - 이메일과 비밀번호가 같은 유저만 로그인 할 수 있다.
        - 로그인에 성공하면 유저에게 토큰 모듈을 통해 토큰을 발급한다.
        - 로그인한 유저만 로그아웃 할 수 있다.
        - 로그아웃에 성공하면 유저의 리프레시 토큰을 삭제한다.
        
## 사용 기술
Node.js, Nest.js, MySQL, Typescript, TypeORM

## RUN
```shell
$ git clone https://github.com/3rd-wanted-pre-onboarding-team-D/02-PayHere-wanted-D.git
$ cd 02-PayHere-wanted-D
$ npm i
$ npm run start
```

## .env 환경변수 설정
```
// mysql
DB_HOST=
DB_USERNAME=
DB_PASSWORD=
DB_DATABASE=

// jwt
JWT_ACCESS_TOKEN_SECRET=
JWT_ACCESS_TOKEN_EXPIRATION_TIME=
JWT_REFRESH_TOKEN_SECRET=
JWT_REFRESH_TOKEN_EXPIRATION_TIME=
```

## API 명세 문서
- Swagger 라이브러리 이용
    - http://localhost:3000/api/
## ERD
<img src='https://user-images.githubusercontent.com/56003992/178000483-efd7e0a5-d1a3-495a-afac-129ee9d2088b.png' width=512>

## DFD
<img src='https://user-images.githubusercontent.com/56003992/178000152-fe542cdc-4ac1-4c70-b33b-66d0cba5eae5.png' width=1024>

## Auth Flow
<img width="512" alt="스크린샷 2022-07-08 오후 9 50 15" src="https://user-images.githubusercontent.com/56003992/178000996-339b1768-8092-443c-9b38-9c8c50e854b0.png">
