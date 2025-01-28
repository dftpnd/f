# Utility Types


```ts
type Partial<Type> = {
  [P in keyof Type]?: Type[P];
};
```


```ts
type Readonly<Type> = {
  readonly [P in keyof Type]: Type[P];
};
```


```ts
type Record<K extends keyof any, Type> = {
  [P in K]: Type;
};
```

```ts
type Pick <Type, K extends keyof Type> = {
  [P in K]: Type[P];
};
```

```ts
type Omit<Type, K extends keyof any> = {
  [P in K]: Type[P];
}
```



# Conditional type

```ts
type status  = 'fail' | 'success' | null | undefined;

type ValidationStatuses<T> = T extends string ? T : never;

type status  ValidationStatuses<status>

```



# Infer

```ts
type MyReturnType<T extends (...args: any[])=> any> = T extends
  (...args: any[])=> infer Return
  ? Return
  : never

type MyParameters<T extends (...args: any[])=> any> = T extends
  (...args: infer Args)=> any
  ? Args
  : never

function Sum(a:number, b:number){
  return a + b;
}

type TestMyReturnType = MyReturnType<typeof Sum>
type TestMyParameters = MyParameters<typeof Sum>
```








