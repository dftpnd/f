## 5

```js
const makePromise = () => {
   return new Promise((resolve, reject)=> {
      reject('Promise rejected')
});
}

makePromise().then(console.log).catch(console.error)
```



## 6. Что такое обьект Promise в JavaScript

1. Средство для работы с асинхронным кодом
2. Способ работы синхронным кодом
3. Обьект для управление потоком сводок
4. Тип данных в JavaScript


## 7. Что выведет консоль (запускаем в браузере)?:

```js
const user = {
   name: "Alice",
   greet: function(){
      console.log('Hello, ', this.name)
   }
}
const greet = user.greet;
greet();
```



## 8. Что выведет в консоль (запускаем в браузере)?

```js
   const array = [1, 2, 3];
   const [first, ...rest] = array;
   
   console.log(first, rest);
```


## 9. Что выведет в консоль (запускаем в браузере)?

```js
   let x = 'var';
   (function(){
      console.log(x);
      let x = 'let';
   })()
```


## 10. Что выведет в консоль (запускаем в браузере)?

```js
   console.log(typeof NaN);
```



## 11. Что делает метод .reduce у массивов?
1. Добавляет элемент в конец массива?
2. Удаляет элемент массива, который удовлетворяет условию
3. Уменьшает длинну массива
4. Итеративно применяет функцию к каждому элементу массива, сводя его к одному значению

## 12. Что выведет в консоль (запускаем в браузере)?

```js
   let arr = [10, 20, 30];
   arr.length = 2;
   console.log(arr)
```

— undefined

— [10, 20, 30]

— [10, 20]

— [10, 20, undefined]


## 13.  Что выведет в консоль (запускаем в браузере)?

```js
  console.log(typeof null)
  console.log(typeof undefined)
  console.log(null === undefined)
```


## 14. Что выведет в консоль (запускаем в браузере)?

```js
  makeFunctionCounter(){
      let count = 0;
      return function(){
         count++;
         console.log(count)
      }
  }

const counter = makeFunctionCounter();
counter();
counter();
```


## 15. Какой метод JSON используется для преобразования обьекта в строку?

— JSON.parse()

— JSON.convert()

— JSON.objectToString()

— JSON.stringify()


## 16. Что выведет в консоль (запускаем в браузере)?


```js
console.log(typeof typeof 1)
```

