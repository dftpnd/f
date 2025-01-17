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

```
   console.log(typeof NaN);
```



## 11. Что делает метод .reduce у массивов?
1. Добавляет элемент в конец массива?
2. Удаляет элемент массива, который удовлетворяет условию
3. Уменьшает длинну массива
4. Итеративно применяет функцию к каждому элементу массива, сводя его к одному значению

## 12. Что выведет в консоль (запускаем в браузере)?

```
   let arr = [10, 20, 30];
   arr.length = 2;
   console.log(arr)
```

— undefined

— [10, 20, 30]

— [10, 20]

— [10, 20, undefined]


## 13

## 14

## 15

## 16
