# BetterJS

BetterJS是D语言的子集，可编译成纯JavaScript，旨在为JavaScript提供强类型支持，提升代码的可维护性。

## 特点
1. 类型检查与类型推断
2. 模板
3. 枚举
4. 元组

所有代码均在`@safe`和`extern (C)`上下文中，该模式下，以下特性不可用：
1. 不安全的特性，如指针运算等、`@trusted`特性
2. 函数重载
3. TypeInfo、ModuleInfo
4. 位域和包含多个字段的联合体
5. `real`类型、向量类型
6. 析构函数、嵌套类
7. 内联asm
8. try后面多个catch
9. Built-in threading & synchronized
10. shared修饰符
11. 除`delete`外的已弃用的特性，如`ucent`等

字符类型将转换为只包含1个字符的字符串
