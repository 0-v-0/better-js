# 速查表

## 变量定义
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
int[3][2] m;
```
</td><td>

```js
let m = [
    [0, 0, 0, ],
    [0, 0, 0, ],
]
```
</td><td>多维数组维度声明顺序与访问的顺序相反</td></tr>
<tr><td>


```d
void[3][2] m;
```
</td><td>

```js
let m = [
    [, , , ],
    [, , , ],
]
```
</td><td>void型多维数组</td></tr>
</table>

## 表达式
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
[a, b] = arr;
```
</td><td>

```js
[a, b] = arr;
```
</td><td>可迭代对象解构赋值</td></tr>
<tr><td>

```d
["foo": bar] = obj;
["user-agent": ua] = header;
([key: a] = obj);
```
</td><td>

```js
({foo: bar} = obj);
({"user-agent": ua} = header);
({[key]: a} = obj);
```
</td><td>对象解构赋值</td></tr>
<tr><td>

```d
assert(1 + 1 == 2, message);
```
</td><td>

```js
console.assert(1 + 1 == 2, message);
```
</td><td>assert表达式</td></tr>
<tr><td>

```d
() => throw new Error("Oops")
```
</td><td>

```js
() => { throw new Error("Oops"); }
```
</td><td>throw表达式</td></tr>
</table>

## 运算符
| BetterJS | JavaScript                                            | 注释     |
| -------- | ----------------------------------------------------- | -------- |
| `a == b` | `a == b`                                              | 相等比较 |
| `a is b` | `a === b`                                             | 全等比较 |
| `a ~ b`  | `a.concat(b)`<br>`a + b`（`a`,`b`可确定为字符串类型） | 连接运算 |
| `a ^^ b` | `a ** b`                                              | 幂运算   |
| `&x`     | `({ [value]: x })`                                    | 取地址   |
| `*p`     | `p[value]`                                            | 解引用   |


## 控制流
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
foreach (x; arr) {
}
```
</td><td>

```js
for (let x of arr) {
}
```

</td><td></td></tr>
</table>


## 函数定义

## 类
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
class A {
    int value;
    string tag = "<untagged>";
    int uninitialized = void;
    static string staticProp = "foo";
    static string staticMethod() {
        return "staticMethod() called";
    }

    // 构造函数
    this(int val) {
        value = val;
    }
}
```
</td><td>

```js
class A {
    value = 0;
    tag = "<untagged>";
    uninitialized;
    static staticProp = "foo";
    static staticMethod() {
        return "staticMethod() called";
    }

    // 构造函数
    constructor(val) {
        this.value = val;
    }
}
```
</td><td>普通类定义</td></tr>
<tr><td>

```d
class A : B {
    this(int id) {
        super(id)
    }
}
```
</td><td>

```js
class A extends B {
    constructor(id) {
        super(id)
    }
}
```
</td><td>继承</td></tr>
<tr><td>

```d
class A : typeof(null) {
}
```
</td><td>

```js
class A extends null {
}
```
</td><td>继承null</td></tr>
<tr><td>

```d
new class Base {
    int id = 2;
}
```
</td><td>

```js
new class extends Base {
    id = 2;
}
```
</td><td>匿名类</td></tr>
</table>

## 接口
