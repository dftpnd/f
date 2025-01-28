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








