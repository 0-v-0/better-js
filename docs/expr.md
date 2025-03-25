# 表达式

## 基本表达式

## 全局常量

`undefined`

## cast表达式

void表达式用`cast(void)`表示，例如`cast(void)0`将编译为`void 0`

除`cast(void)`外，其他cast表达式表示类型断言，例如`f(cast(double)x)`会被编译为`f(x)`

因为JS中没有float类型，因此不支持`cast(float)`


## lambda表达式

```d
const square = (double x) => x * x;
```

```js
const square = (x) => x * x;
```

注意在D语言中lambda表达式是不需要`=>`符号的

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
[a, b] = arr;
```

```js
[a, b] = arr;
```

## 对象解构赋值

若键为Symbol类型或为变量，会自动加上`[]`

对于不包含特殊字符的键名，会自动删除引号

```d
["foo": bar] = obj;
["user-agent": ua] = header;
([key: a] = obj);
```

```js
({foo: bar} = obj);
({"user-agent": ua} = header);
({[key]: a} = obj);
```
