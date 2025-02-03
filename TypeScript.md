https://typescript-exercises.github.io/


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



# Infer 2

```ts
type Token<T> = {
  optional: false
  token: T
}

type TokenOptional<T> = {
  optional: true
  token: T
}

export type TokenType<T> = TokenOptional<T> | Token<T>

export type ExtractType<T> = T extends TokenOptional<infer K>
  ? K | undefined
  : T extends Token<infer R>
    ? R
    : unknown

type SomeType = {
  very: string
  cool: number
}

type A = Token<SomeType>
type B = TokenOptional<SomeType>

type A1 = ExtractType<A>
type B1 = ExtractType<B>
```


# Mapped types

```ts
type Token<T> = {
  optional: false
  token: T
}

type TokenOptional<T> = {
  optional: true
  token: T
}

type TokenType<T> = TokenOptional<T> | Token<T>

type ExtractType<T> = T extends TokenOptional<infer K>
  ? K | undefined
  : T extends Token<infer R>
    ? R
    : unknown

type Question1<T extends Record<string, TokenType<unknown>>> = {
  [PropKey in keyof T]: T[PropKey]['optional'] extends true ? 'da' : 'net'
}

type Question2<T extends Record<string, TokenType<unknown>>> = {
  [PropKey in keyof T]: ExtractType<T[PropKey]>
}

type Question3<T extends Record<string, TokenType<any>>> = {
  [PropKey in keyof T as Exclude<
    PropKey,
    T[PropKey]['optional'] extends true ? PropKey : never
  >]: ExtractType<T[PropKey]>
}

type Question4<T extends Record<string, TokenType<any>>> = {
  [PropKey in keyof T as Exclude<
    PropKey,
    T[PropKey]['optional'] extends true ? PropKey : never
  >]: ExtractType<T[PropKey]>
} & {
  [PropKey in keyof T as Exclude<
    PropKey,
    T[PropKey]['optional'] extends true ? never : PropKey
  >]?: ExtractType<T[PropKey]>
}

type SomeType = {
  very: string
  cool: number
}

type Tokens = {
  a: Token<SomeType>
  b: TokenOptional<SomeType>
  c: Token<SomeType>
  d: TokenOptional<SomeType>
}

type Q1 = Question1<Tokens>
type Q2 = Question2<Tokens>
type Q3 = Question3<Tokens>
type Q4 = Question4<Tokens>

```


