# 表达式

## 基本表达式

## 全局常量

`undefined`

## cast表达式

void表达式`cast(void)`

## lambda表达式

```d
const square = (double x) => x * x;
```

```js
const square = (x) => x * x;
```

```d
const square = (double x) {
    return x * x;
};
```

```js
const square = (x) => {
    return x * x;
};
```

```d
const f = {
    foo();
};
```

```js
const f = () => {
    foo();
};
```

## typeof

用`typeid`代替

## 可迭代对象解构赋值
```d
[a, b] = arr
```

```js
[a, b] = arr
```

## 对象解构赋值
```d
[foo: bar] = obj;
```

```js
({foo: bar} = obj);
```
