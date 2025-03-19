# 关联数组
## 声明与初始化
```d
// 显式类型声明
int[string] wordCount; // 键类型为string，值类型为int

// 字面量初始化
auto colors = [
    "red": "#F00",
    "green": "#0F0",
];
```
以上代码将被编译为
```js
let wordCount = {};
let colors = {
    red: "#F00",
    green: "#0F0",
};
```
对于不包含特殊字符的属性名，会自动删除引号

## 元素操作
```d
// 添加/修改
wordCount["box"] = 5;

// 安全访问
if (auto p = "box" in wordCount) {
    writeln(*p);
}

// 带默认值的访问
auto count = wordCount.get("bug", 0);

// 删除元素
wordCount.remove("bug");
```
与D语言不同，访问不存在的元素并不会引起KeyError

## 遍历元素
```d
foreach (key, value; wordCount) {
    // ...
}

// 仅遍历键
foreach (key; wordCount.keys) {
    // ...
}

// 仅遍历值
foreach (value; wordCount.values) {
    // ...
}
```
以上代码将被编译为
```js
for (let key in wordCount) {
    let value = wordCount[key];
    // ...
}
for (let key of Object.keys(wordCount)) {
    // ...
}
for (let value of Object.values(wordCount)) {
    // ...
}
```

目前不支持数组和除Symbol外的复合类型作为键，请使用Map代替

## 清空数组
以下两种写法并非完全一样
```d
aa = [];
aa.clear();
```
以上代码将被编译为
```js
aa = {};
clear(aa);
```
其中`clear`函数的定义如下
```js
function clear(aa) {
    for (const key in aa) {
        delete aa[key];
    }
}
```
