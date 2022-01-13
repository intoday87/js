# tip
- [히스토리가 없으면 창닫기](https://stackoverflow.com/questions/3588315/how-to-check-if-the-user-can-go-back-in-browser-history-or-not/16580022#16580022)
  ```
  function goBackOrClose() {  

    window.history.back();
    window.close(); 

    throw error('can`t do any thing');
  }
  ```

# es2020 Promise.allSettled
- [MDN doc link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
- `Promise.all`과  `Promise.allSettled`를 번갈아가면서 테스트 해본다. `all`은 한 개라도 reject되면 전체 reject처리, `allSettled`는 어느 하나라도 reject되도 모든 promise를 기다린 후 전체 reject 처리하지 않고 결과를 돌려준다

```js
const result = await Promise.allSettled([
  new Promise((resolve) => {
    setTimeout(() => {
        resolve('promise 1')
        console.log('resolved promise 1')
    }, 1000)
  }),
  new Promise((resolve) => {
    setTimeout(() => { 
        resolve('promise 2')}, 2000)
        console.log('resolved promise 2')
  }),
  new Promise((resolve, reject) => {
    setTimeout(() => {
        reject(new Error('promise 3 got error'))
        console.log('rejected promise 3')
    }, 700)
  })
  ])
console.log('result', result)
```

# [ecma script proposals](https://github.com/tc39/proposals)
- [각 스테이지가 가리키는 의미](https://tc39.es/process-document/)

# research
<ul>
  <li><a target="_blank" href="https://tsh.io/State-of-Frontend-2020-by-TSH.pdf">State of Frontend 2020</a></li>
  <li><a target="_blank" href="https://2020.stateofjs.com/ko-KR/">2020 State Of JS</a></li>
  <li><a target="_blank" href="https://2020.stateofcss.com/ko-KR/">2020 State Of CSS</a></li>
  <li><a target="_blank" href="https://risingstars.js.org/2020/en#section-framework">2020 JavaScript Rising Stars</a></li>
  <li><a target="_blank" href="https://insights.stackoverflow.com/survey/2020">stackoverflow Devloper Survey 2020</a></li>
  <li><a target="_blank" href="https://octoverse.github.com/">GitHub The State of the Octoverse</a></li>
  <li><a target="_blank" href="https://programmers.co.kr/pages/2021-dev-survey">Programmers Dev·Survey 2021</a></li>
</ul>

# Date
## ISO 8601
### Zulu Time Zone - Z
- `2021-04-16T03:40:02.876Z`에서 `Z`는 UTC 시간과 일치하는 시간을 나타낸다 - [wiki](https://ko.wikipedia.org/wiki/ISO_8601#UTC)
- `Z` 없이 `+09:00`으로 타임존을 나타낸다 - [wiki](https://ko.wikipedia.org/wiki/ISO_8601#%ED%91%9C%EC%A4%80_%EC%8B%9C%EA%B0%84%EB%8C%80_%EC%A7%80%EC%A0%95%EC%9E%90(time_zone_designator))

# yarn
- [node_modules로부터 우리를 구원해 줄 Yarn Berry - toss tech](https://toss.tech/article/node-modules-and-yarn-berry)

# 읽어보면 좋을 자료
- [virtual dom 직접 구성해보기](https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Virtual-DOM/#_1-%E1%84%87%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%AE%E1%84%8C%E1%85%A5-%E1%84%85%E1%85%A9%E1%84%83%E1%85%B5%E1%86%BC-%E1%84%80%E1%85%AA%E1%84%8C%E1%85%A5%E1%86%BC)
- [2016년에 자바스크립트를 배우는 기분](http://www.looah.com/article/view/2054)
  - 현재 히스토리를 jquery 사용이 퇴보하는 시점부터 재미있게 대화 형식으로 잘 정리한 

# 취약점 분석 - snyk.io에서 취약점 DB 조회
- https://security.snyk.io/page/1?q=next&type=npm
