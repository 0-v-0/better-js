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

## 示例

```d
module demo;

import betterjs;
import foo.bar : func = test;

// 枚举
enum Direction : string {
    none = "auto",
    bottom = "bottom",
    top = "top",
}
// 类
export class ToolTip : HTMLElement {
    static observedAttributes = ["color"];

    @property {
        string color() => getAttribute("color") || "";
        void color(string value) => setAttribute("color", value);
        Direction dir() => getAttribute("dir") || Direction.none;
        void dir(string value) => setAttribute("dir", value);
    }

	this() {
		super();
		const shadowRoot = attachShadow(["mode": "open"]);
		shadowRoot.innerHTML = import("./tool-tip.html");
	}

	void connectedCallback() {
		if (dir == Direction.none)
            initDirection();
        func();
	}

    // 私有方法
    private void initDirection() {
        alias h = document.body.scrollHeight;
		enum TIP_SIZE = 50;
        with (getBoundingClientRect()) {
			if (top < TIP_SIZE)
				dir = Direction.bottom;
			else if (h - top - height < TIP_SIZE)
				dir = Direction.top;
        }
    }
}

static this() {
    customElements.define("tool-tip", Class!ToolTip);
}
```

以上代码编译为JavaScript:

```js
import { test as func } from 'foo/bar.js';

export class ToolTip extends HTMLElement {
	static observedAttributes = ["color"]
	get color() { return this.getAttribute("color") || ""; }
	set color(value) { this.setAttribute("color", value); }
	get dir() { return this.getAttribute("dir") || "top"; }
	set dir(value) { this.setAttribute("dir", value); }
	constructor() {
		super();
		const shadowRoot = this.attachShadow({ mode: "open" });
		shadowRoot.innerHTML = "...<html string>";
	}
	connectedCallback() {
		if (this.dir == "auto")
            this.#initDirection();
        func();
	}
    #initDirection() {
        const { top, height } = this.getBoundingClientRect()
        if (top < 50)
            this.dir = "bottom";
        else if (document.body.scrollHeight - top - height < 50)
            this.dir = "top";
    }
}
customElements.define("tool-tip", ToolTip)
```

## TODO
- [ ] 声明时解构赋值：`const [a,b] = arr`
- [ ] `foreach (ref x; arr)`
- [ ] scope语句
- [ ] sourcemap

## 参考
- [dtojs](https://github.com/adamdruppe/dtojs)
