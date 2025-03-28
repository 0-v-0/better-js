# 基本词法
词汇分析独立于句法分析和语义分析。词法分析器将源文本拆分为标记。词法语法描述了这些标记的语法。该语法被设计为适用于高速扫描，并有助于实现正确的扫描器。它有最低限度的特殊情况规则，只有一个翻译阶段。


## 整数

C风格的八进制整数表示法（例如0167）被认为太容易与十进制表示法混淆；只有字符串字面量才完全支持它

十六进制浮点值前面是0x或0X，指数是P或p，后面是用作2的指数的十进制数

```d
1f;  // float
1.f; // UFCS语法，相当于f(1)
1.;  // double
```

## 关键字
关键字是保留的标识符

## 源代码

### 编码
只允许以下编码
- ASCII (7位 ASCII)
- UTF-8
- UTF-16
- UTF-32

UTF-8源文件不以BOM开头
### 文件尾
文件尾后面的任意内容不属于源码
```d
__EOF__
这里的内容会被忽略
```


### 行尾
`\u000D`（CR）、`\u000A`（LF）、`\u000D\u000A`（CR LF）、`\u2028`、`\u2029`、文件尾

### 空白
`\x20`、`\x09`、`\x0B`、`\x0C`

## 注释
以下3种
1. 行注释（`// ...`）在行尾终止
2. 块注释（`/* ... */`）可跨行，但不能嵌套
3. 嵌套块注释（`/+ ... +/`）可跨行，可嵌套

注释不能用作标记连接符

## 标识符
通用

标识符长度不能超过255个字符，并且区分大小写

两个下划线开头的标识符是保留的


## 符号
## 数字
### 整数
### 浮点数

## 字符
### 转义字符

## 字符串

在所有字符串文本形式中，行尾被视为单个字符

### 原始字符串
所见即所得字符串
字符串中没有转义序列

反引号

### 双引号字符串


### 定界字符串

分隔字符串使用各种形式的分隔符

如果分隔符是标识符，则标识符后面必须紧跟一个换行符，并且匹配的分隔符必须是从该行开头开始的同一标识符

### 块字符串

### 字符串后缀

```d
"hello"c  // string
"hello"w  // wstring
"hello"d  // dstring
```

### 关键字

### 魔术常量

### 特殊符号序列
特殊的令牌序列由词法分析器处理，可以出现在任何其他令牌之间，并且不影响语法解析。
特殊令牌序列由序列开头第一个#令牌后面的第一个换行符终止。
目前只有一个特殊的令牌序列，`#line`。