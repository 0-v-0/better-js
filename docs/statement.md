# 语句

## 变量声明

`immuable s = Symbol();`，这里`s`的类型相当于TypeScript中的`unique symbol`

`extern`修饰的声明不产生代码

## 变量初始化

BetterJS中未初始化的变量将被初始化为默认值，例如：
```d
int n;
```
```js
let n = 0;
```

若无需初始化变量，请使用void初始化，例如：
```d
int x = void;
```
```js
let x;
```

## 作用域

## foreach
foreach将编译为for of或in
```d
foreach (x; arr) {
}
```

```js
for (let x of arr) {
}
```

若需要指定foreach的变量不可变，可用const修饰变量：

```d
foreach (const x; arr) {
}
```

```js
for (const x of arr) {
}
```

若需要编译为for in，请使用`keys`属性
```d
foreach (key; obj.keys) {
}
```

```js
for (let key in obj) {
}
```

目前不支持`ref`修饰变量，例如`foreach (ref x; arr)`
