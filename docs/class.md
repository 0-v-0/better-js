# 类与接口

## 类的定义
语法
```d
class A {
    int field;

    // 构造函数
    this(int value) {
        field = value;
    }
}
```

```js
class A {
    field;

    // 构造函数
    constructor(value) {
        field = value;
    }
}
```

不支持嵌套类

## 构造函数
构造函数是一种特殊的函数，其名称为`this`，且不需要声明返回类型

BetterJS中不支持析构函数

## 静态成员
可以用`static`关键字定义静态方法或字段。

静态构造函数属于一种特殊的静态方法，它不能有参数。

语法
```d
class A {
    static string staticProperty = "someValue";
    static string staticMethod() {
        return "static method has been called.";
    }
    static int field = 1;

    static this() {
        console.log('Class static initialization block called');
    }
}
```

```js
class A {
    static staticProperty = "someValue";
    static staticMethod() {
        return "static method has been called.";
    }

    static {
        console.log('Class static initialization block called');
    }
}
```

## 继承
BetterJS使用`:`代替JS中的extends关键字

在JS中允许`extends null`，在BetterJS中的等效写法如下
```d
class A : typeof(null) {
    /* ... */
}
```

## 私有成员
类的私有成员包括私有字段和私有方法。

私有成员在编译为JS后会自动加上前缀`#`。

和D语言不同，在BetterJS中，类中定义的私有成员只能在类内访问，而不是该文件内可访问，若需要实现仅该文件内可访问，最接近的做法是使用`package(当前包名)`代替。

## 抽象类
抽象类使用`abstract`关键字定义，它只能被继承，不能被实例化
```d
abstract class A {
    void abstractMethod();
}
```

## 匿名类

```d
new class Base {
    int foo = 2;
}
```

```js
new class extends Base {
    foo = 2;
}

```

## 接口
接口中只能定义方法，不含函数体的方法为抽象方法，包含函数体的方法必须用final修饰，例如：
```d
interface I {
    void func();
}
```
不包含final方法的接口将不会产生代码。
