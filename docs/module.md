# 模块

除特别说明外，本页中，前面的代码为BetterJS，后面的为编译结果

## 模块导入

```d
import foo.bar;
```

```js
import 'foo/bar.js';
```

导入全部

```d
static import a = mod;
```

```js
import * as a from 'mod';
```

局部导入将会自动提升到顶层作用域，若与顶层作用域的符号冲突，编译器将自动重命名局部导入的符号

## 导出符号
导出单个符号
```d
export alias a = a;
```

```d
export { a }
```
导出多个符号
```d
export alias a = a;
```

```d
export { a }
```

## export复合写法

```d
export import mod : foo, bar;
```

```js
export { foo, bar } from 'mod';
```

重命名再导出

```d
import mod : foo, b = bar;
```

```js
export { foo, bar as b } from 'mod';
```

默认导出

```d
export import mod : __default;
```

```js
export { default } from 'mod';
```

重命名默认导出

```d
export import mod : a = __default;
```

```js
export { default as a } from 'mod';
```

导出全部

```d
export static import a = mod;
```

```js
export * as a from 'mod';
```

## import()与import.meta

- `import()`使用`__import()`代替
- `import.meta`使用`__import.meta`代替
