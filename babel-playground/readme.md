# babel
ES6으로 작성된 코드를 IE를 포함한 모든 브라우저에서 문제없이 동작하기 위해 사용하는 트랜스파일러.(ES6 -> ES5)

# polyfill(폴리필)
비호환 브라우저에 없는 코드의 기능을 지원하기 위해서 삽입하는 코드 조각이나 플러그인으로 babel보다 번거로운 기능이다. 
HTML5 및 CSS3와 오래된 브라우저를 호환시키기 위해서도 많이 사용한다.


- [폴리필을 사용하는 보다 쉬운 방법](http://hacks.mozilla.or.kr/2014/12/an-easier-way-of-using-polyfills/)


# babel 설치
```
npm init -y
npm install babel-cli --save-dev

```

# pacakge.json
- 불필요한 설정 삭제 후 아래와 같다.

```
{
  "name": "babel-project",
  "version": "1.0.0",
  "devDependencies": {
    "babel-cli": "^6.26.0"
  }
}
```

# preset 설치
```
npm install babel-preset-env --save-dev
```

# .babelrc 설정 파일 작성
- env reset 설정하기
```
{
  "presets": ["env"]
}
```


## babel CLI
```npm install babel-cli --save-dev```

### --save-dev와 --save의 차이
 --save 옵션은 dependencies object에 추가하고 --save-dev 옵션은 devDepenencies object에 추가한다.

 1) 테스트 관련 모듈이나 트랜스 파일러 관련 모듈은 dependencies 개체에 추가하면 안된다. 
 2) 운영이 아닌 개발 단계에서만 필요한 의존성 모듈들은 devDependencies에 설치해야 한다.
 3) 즉, --save로 설치된 모듈은 설치배포용이다.


 ## 트랜스파일링 옵션
 -w(--watch) : 파일 변경을 감지하여 자동으로 트랜스파일한다.
 -d(--out-dir) : 출력 파일이 저장될 폴더를 지정한다.
 
 ``` 
 babel src/js -d dist/js -w
 ```
 - src/js 폴더에 ES6 코드를 작성하고 변환된 코드는 dist/js 폴더에 저장한다. 
 - src폴더 내의 파일의 변경된 내용을 감지해서 자동으로 변환작업을 수행하도록 -w 옵션을 적용한다.

 ## package.json
 package.json 파일의 scripts에 추가

 ``` "build" : "babel src/js -w -d dist/js"``` 

- src/js 폴더의 ES6를 트랜스파일링한 후, dist/js 폴더에 저장한다.
- 트랜스파일링 실행 : npm run build
