# 语句

## 变量声明

`immuable s = Symbol();`，这里`s`的类型相当于TypeScript中的`unique symbol`

`extern`修饰的变量为变量声明，将不会产生代码

## 变量初始化

BetterJS中未初始化的变量将被初始化为默认值，例如：
```d
int n;
```
```js
let n = 0;
```

若需要将变量初始化为`undefined`，请使用void初始化，例如：
```d
int x = void;
```
```js
let x;
```

## 作用域

## 顶层语句
在BetterJS中不支持顶层语句，需要将顶层语句写在模块构造函数中
```d
static this() {
  foo();
}
```
```js
foo();
```

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

若需要编译为for in，请使用`__in`函数
```d
foreach (key; __in(obj)) {
}
```

```js
for (let key in obj) {
}
```

目前不支持`ref`修饰变量，例如`foreach (ref x; arr)`
