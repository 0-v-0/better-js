# 异常处理

## 异常和错误的概念
在编程中，异常是指在程序执行过程中发生的错误或异常情况。当程序遇到异常时，会中断当前的执行流程，并跳转到异常处理的代码块中进行处理。

## try-catch-finally语句
语法
```d
try {
    // 可能会抛出异常的代码
} catch (ExceptionType e) {
    // 处理异常的代码
} finally {
    // 无论是否发生异常都会执行的代码
}
```
try块中包含可能会抛出异常的代码，catch块用于捕获并处理异常，finally块中的代码无论是否发生异常都会执行。

若块中只包含一条语句，则可以省略大括号。

## scope语句
用于在指定的作用域内处理异常。当异常发生时，scope语句中的代码会被执行，并且在离开作用域时自动销毁。

```d
scope(exit) {
    // 可能会抛出异常的代码
}
```

## 异常
异常(Exception)和错误(Error)是不同的概念。异常是指在程序执行过程中发生的非正常情况，而错误是指在编译过程中发生的问题。异常是可以被捕获和处理的，而错误则需要在编译前修复。

## 自定义异常类
除了使用内置异常类外，我们还可以自定义异常类来表示特定的异常情况。自定义异常类需要继承自Exception类，并实现自己的构造函数和toString方法。

```d
class MyException : Exception {
    this(string message) {
        super(message);
    }

    override string toString() const {
        return "MyException: " ~ message;
    }
}
```

## assert表达式
assert表达式用于检查程序中的错误和异常情况，将被编译为`console.assert`。

语法
```d
assert(expression, message);
```
以上代码编译结果：
```js
console.assert(expression, message);
```
