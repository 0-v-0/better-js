# 类型

## 基本数据类型

基本数据类型分为void和标量类型，void只能用于函数返回类型、类型比较和类型转换，不能作为变量类型。

标量类型是指只能存储单个值的数据类型。D语言提供了以下标量类型：

- 布尔类型：`bool`，默认值为`false`
- 整数类型：`byte`、`ubyte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`，默认值为0
- 浮点数类型：`float`、`double`、`real`，默认值为`NaN`
- 字符类型：`char`、`wchar`、`dchar`，默认值分别为'\xFF'、'\uFFFF'、'\U0000FFFF'

## 派生数据类型

## typeof

## 特殊类型

- `any`：可转换为任意类型
- `typeof(null)`：属于引用类型，其值只能为`null`，`typeof(null).sizeof`等于size_t.sizeof
- `noreturn`：相当于TypeScript中的`never`

## 内置类型
内置类型在`betterjs.core`包中，包括以下类型：
1. Object
2. Array
3. BigInt

## 内置类型工具
内置类型工具在`betterjs.typecons`包中，包括以下模板：
Awaited

Exclude!(Type, ExcludedMembers)

Extract

InstanceType

