# .bind

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
