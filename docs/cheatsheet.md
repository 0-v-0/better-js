# 速查表

## 变量定义

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
</table>

## 运算符
| BetterJS | JavaScript         | 注释 |
| -------- | ------------------ | ---- |
| `a == b` | `a == b`           |      |
| `a is b` | `a === b`          |      |
| `&x`     | `({ [value]: x })` |      |
| `*p`     | `p[value]`         |      |


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
