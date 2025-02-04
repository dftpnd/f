# bind polyfill

```ts
Funtion.proptotype.bind = funtion(context){
	const func = this;
	return function(…args) {

		return func.apply(
			context,
			args
		);
	}
}
```



# filter polyfill

```ts
Array.prototype.filter = function (callback) {
  //Store the new array
  const result = [];
  for (let i = 0; i < this.length; i++) {
    //call the callback with the current element, index, and context.
    //if it passes the text then add the element in the new array.
    if (callback(this[i], i, this)) {
      result.push(this[i]);
    }
  }
  
  //return the array
  return result
}
```
