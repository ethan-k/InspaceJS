# NPM 사용 설명문


## npm 이란?
Node Package Modules

npm init 으로 package.json 파일 생성

![Image of NPM Init](img/npm_init.png)

#### package.json 에 미리 정의된 파일 설치

npm install

#### npm 에 전역 의존성 추가

    npm install -g 패키지이름

    ex) npm install -g webpack

#### npm 에 개발 로컬 의존성 추가

1. 프로덕션에 필수 적인 경우

        npm install 패지이름 --save

        ex) npm install jquery --save


2. 개발용 의존성 추가시

        npm install 패키지이름 --save-dev
