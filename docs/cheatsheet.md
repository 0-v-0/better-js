# 速查表

## 变量定义
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
int n;
```
</td><td>

```js
let n = 0;
```
</td><td>未初始化的变量将被初始化为默认值</td></tr>
<tr><td>

```d
string s;
```
</td><td>

```js
let s = '';
```
</td><td>字符串默认初始化为空串</td></tr>
<tr><td>

```d
double x;
```
</td><td>

```js
let x = NaN;
```
</td><td>浮点型默认初始化为NaN</td></tr>
<tr><td>

```d
char c;
wchar w;
```
</td><td>

```js
let c = '\xff';
let w = '\uffff';
```
</td><td>字符类型默认初始化为最大值</td></tr>
<tr><td>

```d
int x = void;
```
</td><td>

```js
let x;
```
</td><td>无需初始化的变量赋值void</td></tr>
<tr><td>

```d
extern int e;
```
</td><td>

```js
/* no code */
```
</td><td>extern修饰的声明不产生代码</td></tr>
<tr><td>

```d
int[] list;
```
</td><td>

```js
let list = [];
```
</td><td>数组</td></tr>
<tr><td>

```d
int[2] pair;
```
</td><td>

```js
let pair = [0, 0];
```
</td><td>静态数组</td></tr>
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
<tr><td>


```d
int[string] map;
```
</td><td>

```js
let map = {};
```
</td><td>关联数组</td></tr>
</table>

## 表达式
<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
[1, 2]
```
</td><td>

```js
[1, 2]
```
</td><td>数组字面量</td></tr>
<tr><td>

```d
["day": 2]
```
</td><td>

```js
{day: 2}
```
</td><td>对象字面量</td></tr>
<tr><td>

```d
const f = {
    console.log("f()");
}
```
</td><td>

```js
const f = () => {
    console.log("f()");
}
```
</td><td>无参函数字面量</td></tr>
<tr><td>

```d
const square = (double x) {
    return x * x;
};
```
</td><td>

```js
const square = (x) => {
    return x * x;
};
```
</td><td>函数字面量</td></tr>
<tr><td>

```d
const square = (double x) => x * x;
```
</td><td>

```js
const square = (x) => x * x;
```
</td><td>lambda表达式</td></tr>
<tr><td>

```d
const f = function() {
    foo();
};
```
</td><td>

```js
const f = function() {
    foo();
};
```
</td><td>函数指针</td></tr>
<tr><td>

```d
const f = delegate() {
    foo();
};
```
</td><td>

```js
const f = function() {
    foo();
};
```
</td><td>委托</td></tr>
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
<tr><td>

```d
is(double : int)
```
</td><td>

```js
false
```
</td><td>is表达式</td></tr>
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
if (auto val = node.value) {
}
```
</td><td>

```js
let val = node.value
if (val) {
}
```

</td><td>条件中变量声明</td></tr>
<tr><td>

```d
if (const val = node.value) {
}
```
</td><td>

```js
const val = node.value
if (val) {
}
```

</td><td>条件中常量声明</td></tr>
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

</td><td>for of</td></tr>
<tr><td>

```d
foreach (const x; arr) {
}
```
</td><td>

```js
for (const x of arr) {
}
```

</td><td>for of (const)</td></tr>
<tr><td>

```d
foreach (key; obj.keys) {
}
```
</td><td>

```js
for (let key in obj) {
}
```

</td><td>for in</td></tr>
</table>


## 函数

<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
int add(int a, int b) { return a + b; }
```
</td><td>

```js
function add(a, b) { return a + b; }
```

</td><td>函数定义</td></tr>
<tr><td>

```d
int add(int a, int b) => a + b;
```
</td><td>

```js
function add(a, b) { return a + b; }
```

</td><td>简化版函数定义</td></tr>
<tr><td>

```d
add(2, 3);
```
</td><td>

```js
add(2, 3);
```

</td><td>函数调用</td></tr>
<tr><td>

```d
add(a: 2, b: 3);
```
</td><td>

```js
add(2, 3);
```

</td><td>具名参数</td></tr>
</table>

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
    static string test() {
        return "test() called";
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
    static test() {
        return "test() called";
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
</td><td>继承使用:代替extends</td></tr>
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

<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
interface Bell {
    void beep();

    final void test() {
        console.log("test");
    }
}
```
</td><td>

```js
class Bell {
    test() {
        console.log("test");
    }
}
```
</td><td>抽象方法不会产生代码</td></tr>
</table>

## 模块

<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
import foo.bar;
```
</td><td>

```js
import 'foo/bar.js';
```

</td><td>导入模块</td></tr>
<tr><td>

```d
static import a = mod;
```
</td><td>

```js
import * as a from 'mod';
```

</td><td>导入全部</td></tr>
<tr><td>

```d
export alias a = a;
```
</td><td>

```js
export { a }
```

</td><td>导出单个符号</td></tr>
<tr><td>

```d
export alias a = a,
    b = b;
```
</td><td>

```js
export { a, b }
```

</td><td>导出多个符号</td></tr>
<tr><td>

```d
export import mod : foo, bar;
```
</td><td>

```js
export { foo, bar } from 'mod';
```

</td><td>重新导出</td></tr>
<tr><td>

```d
import mod : foo, b = bar;
```
</td><td>

```js
export { foo, bar as b } from 'mod';
```

</td><td>重命名再导出</td></tr>
<tr><td>

```d
export import mod : __default;
```
</td><td>

```js
export { default } from 'mod';
```

</td><td>默认导出</td></tr>
<tr><td>

```d
export import mod : a = __default;
```
</td><td>

```js
export { default as a } from 'mod';
```

</td><td>重命名默认导出</td></tr>
<tr><td>

```d
export static import a = mod;
```
</td><td>

```js
export * as a from 'mod';
```

</td><td>导出全部</td></tr>
<tr><td>

```d
__import('a.js')
```
</td><td>

```js
import('a.js')
```

</td><td>动态import</td></tr>
<tr><td>

```d
__import.meta
```
</td><td>

```js
import.meta
```

</td><td>import.meta</td></tr>
<tr><td>

```d
static this() {
    foo();
}
```
</td><td>

```js
foo();
```

</td><td>顶层语句</td></tr>
</table>

## 结构体

本节所使用的结构体定义
```d
struct Point {
    int x, y;
}
struct Uninit {
    int x, y = void;
}
```

<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
Point p;
Uninit u;
```
</td><td>

```js
let p = {x: 0, y: 0};
let u = {x: 0};
```
</td><td>结构体默认初始化</td></tr>
<tr><td>

```d
auto p = Point(2, 1);
```
</td><td>

```js
let p = {x: 2, y: 1};
```
</td><td>结构体初始化</td></tr>
<tr><td>

```d
auto p = Point(2);
```
</td><td>

```js
let p = {x: 2, y: 0};
```
</td><td>结构体部分初始化</td></tr>
<tr><td>

```d
Point p = {x: 2, y: 1};
```
</td><td>

```js
let p = {x: 2, y: 1};
```
</td><td>结构体字面量初始化</td></tr>
</table>

## 别名与模板

<table>
<tr><td>BetterJS</td><td>JavaScript</td><td>注释</td></tr>
<tr><td>

```d
alias x = a;
add(x, b);
```
</td><td>

```js
add(a, b);
```
</td><td>别名会在编译时展开</td></tr>
<tr><td>

```d
alias args = AliasSeq!(1, 2);
add(args);
```
</td><td>

```js
add(1, 2);
```
</td><td>元组序列</td></tr>
<tr><td>

```d
T add(T)(T a, T b) { return a + b; }
```
</td><td>

```js
function add(a, b) { return a + b; }
```

</td><td>函数模板</td></tr>
<tr><td>

```d
T add(T: double)(T a, T b) { return a + b; }
```
</td><td>

```js
function add(a, b) { return a + b; }
```

</td><td>模板约束</td></tr>
</table>