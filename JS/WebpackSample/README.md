# Webpack 사용법

## Webpack이란?

Webpack은 모듈 번들러로서 자바스립트외에도 개발에 쓰이는 다양하 파일들로 모듈별로 관리하고 합쳐준다.

ES6 loader 로더를 통해서 ES6문법을 사용해서 브라우저에서 사용할수 있게 해주는 프로그램이라고 보면된다


## Webpack 설치
아래 명령어를 통하여 설치

    npm install webpack --save

    // 전역적으로 설치하고 싶은 경우

    npm install -g webpack

루트 프로젝트에 webpack.config.js 파일을 생성하고 아래 와 같이 설정한다
webpack은 실행시 컨피그 옵션이 없으면  wepback.config.js 를 디폴트로 찾게된다.
```javascript
module.exports = {
  context: path.resolve(__dirname, './src'), // 소스 디렉토리 루트 폴더 위치
  entry: './entry.js',
  output: {
    path: __dirname,
    filename: 'bundle.js'
  }
};
```

context 폴더는 베이스 폴더의 개념으로 webpack이 소스파일들을 추적하는 곳의 root 폴더 역할을 한다.
위 설정파일의 경우 프로젝트 루트 폴더에 설정된다

```
├── project/
│   ├── package.json
│   ├── lib
│   │   ├── moduleA.js
│   ├── components
│   │   ├── print.js
```

## ES6 사용

```
npm install --save babel-loader babel-core babel-preset-es2015
```

```javascript
module.exports = {
  entry: './entry.js',
  output: {
    path: __dirname,
    filename: 'src/js/dist/bundle.js'
  },
  module: {
       loaders: [
            {
                test: /\.js$/,
                loader: 'babel',
                exclude: /(node_modules|bower_components)/,
                query: {
                    presets: ['es2015']
                }
            }
       ]
  }
};
```
