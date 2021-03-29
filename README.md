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
- todo 각 스테이지가 가리키는 
