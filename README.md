# 


```js
const makePromise = () => {
   return new Promise((resolve, reject)=> {
      reject('Promise rejected')
});
}

makePromise().then(console.log).catch(console.error)
```
