# webpack
- javascript 모듈화 도구
- javascript 언어 자체가 지원하는 모듈 시스템이 없기 때문에 그 한계를 극복하려고 활용하는 도구 중 하나가 webpack이다.(gulp, grunt 등)


# Module?
- 파일 단위로 분리되 있으며 필요에 따라 애플리케이션은 명시적으로 모듈을 로드한다.
- 서버에서 처리하는 로직은 javascript로 구현하는 부분이 많아지면서 javascript 코드의 양이 늘어났다.
코드의 양이 많아지면 코드의 유지와 보수가 쉽도록 코드를 모듈로 나누어 관리하는 모듈 시스템이 필요해진다.
- JavaScript 모듈화은 크게 CommonJS 진영과 AMD 진영으로 나뉘게 되었고 브라우저에서 모듈을 사용하기 위해서는 CommonJS 또는 AMD를 구현한 모듈 로더 라이브러리를 사용하여야 되는 상황이 되었다. => [CommonJS와 AMD에 관해서 참고](http://d2.naver.com/helloworld/12864)



# babel 6 & webpack3 환경 구축

1) babel설치 및 환경 설정
- 트랜스파일링(ES5로 변환), 모듈은 지원하지 않음
2) webpack 설치 및 트랜스파일링 설정
- 하나의 파일로 번들링
- npm install webpack --save-dev
- npm install babel-loader --save-dev
3) package.json scripts 변경
- "build": "webpack -w"
- 변경된 내용이 watch를 통해 바로 적용됨
4) webpack.config.js을 생성
- 모듈 전후 파일이 저장될 경로와 규칙
5) 번들링 실행
- npm run build
- 3개의 js모듈이 하나로 번들된 bundle.js가 실행된다.