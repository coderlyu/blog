---
title: JavaScript总结
date: '2026-03-01 18:07:19'
head: []
outline: deep
sidebar: false
prev: false
next: false
---



# JavaScript总结

# 基础

1. 数据类型

   1. 原始类型：number、string、boolean、undefined、null、bigint、symbol
   2. 引用类型：Object、Array、Date...
2. 数据类型检测

   1. 原始类型用 typeof ，除了null：`typeof null === ‘object’`
   2. 引用类型用 instanceof；基于原型链判断：`{} instanceof Object === true`

      1. instanceof的实现原理：检查构造函数的 `prototype` 是否出现在对象的原型链中
   3. ​`Object.prototype.toString.call`​：判断所有类型： `Object.prototype.toString.call(new Date) === '[object Date]'`
3. NaN是什么

   1. not a number
   2. NaN ！== NaN，用 Number.IsNaN() 来判断
4. 0.1 + 0.2 !== 0.3 问题

   1. 在底层用二进制来存储数字，有些会被存储为无限循环小数，由于精度限制而截断，导致存储误差
   2. 解决：放大倍数计算、用高精度库(big.js)、转成字符串计算、用 `toFixed`
5. 类型转换

   1. 强制类型转换：Number()、parseInt()
   2. 隐式类型转换：`1 + '1' === '11'`（字符串拼接）
   3. ​ **​`==`​** ​ **vs**  **​`===`​** ：前者会触发隐式转换，后者要求类型和值完全一致。
6. 虚值和真值

   1. 虚值：**在转换为**​**[布尔值](https://zhida.zhihu.com/search?content_id=235535084&content_type=Article&match_order=1&q=%E5%B8%83%E5%B0%94%E5%80%BC&zhida_source=entity)**​**时** 变为 **false** 的值，
   2. 真值：**在转换为**​**[布尔值](https://zhida.zhihu.com/search?content_id=235535084&content_type=Article&match_order=1&q=%E5%B8%83%E5%B0%94%E5%80%BC&zhida_source=entity)**​**时** 变为 **true** 的值
7. && 和 |｜

   1. &&： 逻辑与，全为真才是真。
   2. |｜：逻辑或，只要有一个为真。
8. a = i++ 和 a = ++i

   1. i++：先赋值a = i，再计算 i = i + 1。
   2. ++i：先计算 i = i + 1，再进行赋值a = i。
9. 变量提升和函数提升

   1. 变量提升

      1. var：声明会被提升到作用域顶部，但**赋值不会**。在声明前访问会得到 `undefined`。
      2. const、let：`let`​ 和 `const`​ 声明也会被提升，但在初始化之前不允许访问。面试官常问：“`let`​ 到底有没有提升？”（**答案是有提升，但没有初始化，处于死区**）。【**暂时性死区：** <span data-type="text" style="background-color: var(--b3-font-background12);">因未初始化而不可被访问的阶段，</span>抛出 `ReferenceError` 错误】
   2. 函数提升

      1. ​**函数声明（Function Declaration）** ​：会被​**完整提升**。你可以在声明行之前调用该函数。
      2. **函数表达式（Function Expression）** ：如果是用 `var`​ 定义的，仅变量名提升，值为 `undefined`​，此时调用会报错 `TypeError: ... is not a function`。
   3. 同名的变量和函数同时提升时优先级？

      1. **函数优先**：函数声明的提升权重高于变量声明（var）。
      2. **后续赋值覆盖**：提升只是确定了“坑位”，代码执行阶段的**赋值操作**会覆盖之前的声明。
10. let、const、var区别

    1. ​**区别**：var为函数级作用域，可重复声明/提升；let/const为块级作用域，不可重复声明。
    2. ​**提升**：var提升并初始化为undefined，let/const提升但不初始化（死区）。
    3. **const特性**：必须初始化，不能重新赋值（对象属性可修改）。
11. 执行上下文：<span data-type="text" style="background-color: var(--b3-font-background7);">执行上下文是 JavaScript 代码被解析和执行时所在环境的抽象概念</span>

    1. 全局执行上下文和函数执行上下文
    2. 生命周期

       - ​**创建阶段 (Creation Phase)** ：

         - ​**生成变量对象 (VO/AO)** ​：扫描 `var`​ 变量（设为 `undefined`​）和函数声明（全量提升）——这就是**变量提升**的本质。
         - ​**建立作用域链 (Scope Chain)** ：确定当前环境可以访问哪些外部变量。
         - ​**确定** **​`this`​**​ **指向**​：绑定当前执行环境的 `this`。
       - ​**执行阶段 (Execution Phase)** ：

         - 逐行执行代码，完成变量赋值和函数执行
12. 作用域和作用域链（考察变量可访问性、查找规则及闭包）

    1. 作用域：JS中变量和函数的有效访问范围（全局、函数、ES6块级）。
    2. 作用域链：在当前作用域查找变量，找不到就沿父作用域向上查找，直到全局，这个逐级查找的过程就是作用域链。
13. 闭包

    1. 闭包是指有权访问另一个函数作用域中变量的**函数**。
    2. 使用场景：数据私有化、柯里化、高级函数（防抖、节流、回调）、模块化
    3. 防止内存泄露：在闭包不再使用时，手动将其引用设为 `null`，触发垃圾回收。
14. 事件模型（**传播机制、代理模式、兼容性及性能优化**）

    1. 事件流【`addEventListener`​​​​​​​​​​<span data-type="text" style="background-color: var(--b3-font-background12);"> 的第三个参数。</span>`false`​​​​​​​​​​<span data-type="text" style="background-color: var(--b3-font-background12);">（默认）表示在冒泡阶段触发</span>】

       1. 捕获阶段：从 `window` 对象开始，自上而下向目标节点传播
       2. 目标阶段：事件到达实际触发的元素
       3. 冒泡阶段：从目标节点开始，自下而上向 `window` 对象传播。
       4. 区别：`event.target`​ 是触发事件的实际元素，`event.currentTarget` 是绑定事件的元素
    2. 委托/代理

       1. **原理**：利用事件**冒泡**机制，将事件监听器绑定在父元素上，通过 `event.target` 判断具体触发的子元素
       2. 优点：**内存优化**：减少监听器数量。 **动态性**：新增的子元素无需重新绑定事件。
    3. DOM事件级别

       1. **DOM0**：`onclick = function(){}`。缺点是同一元素只能绑定一个同类事件，会被覆盖。
       2. **DOM2**：`addEventListener`。支持绑定多个事件，支持指定捕获/冒泡。
       3. **DOM3**：在 DOM2 基础上增加了更多的事件类型（如焦点、鼠标滚轮、UI 事件）
    4. 常用事件

       1. ​**​`stopPropagation`​**：阻止冒泡
       2. ​**​`preventDefault`​**：阻止默认行为（页面滚动、链接跳转或粘贴文本）
       3. ​**​`stopImmediatePropagation`​**​：**完全阻断事件传播**。它不仅能像 `stopPropagation()`​ 一样阻止事件冒泡到父元素，还能阻止**同一元素**上绑定的其他同类型事件监听器执行
15. 事件循环

    1. 概念：是 JavaScript 处理异步任务的机制
    2. 宏任务：setTimeout、setInterval、I/O、UI渲染
    3. 微任务：promise、async/await、`process.nextTick`
    4. 执行流程是【同步代码 -\> 微任务队列 -\> 宏任务队列 -\> 重新渲染】

       1. 执行同步代码
       2. 执行每一个宏任务之前优先清空微任务队列
    5. dom事件是宏任务：同步代码 -\> 微任务清空 -\> **DOM事件回调(宏任务)**  -\> 微任务清空 -\> 下一个宏任务。
16. this指向

    1. 函数独立调用默认是window
    2. 方法调用指向最后调用的对象
    3. 用 `new`​ 调用构造函数，`this`​ 指向**新创建的实例对象**。
    4. call、apply、bind指向绑定的对象
17. 箭头函数和普通函数

    1. this指向不同：箭头函数this由外部作用域确定；普通函数是谁调用指向谁。
    2. 箭头函数没有this不能作为构造函数，普通函数可以
    3. 普通函数有`arguments`，箭头函数用es6剩余参数
    4. 箭头函数**不能用作生成器，** 不能用`yield`
18. 函数式编程理解

    1. 概念：函数式编程是一种编程范式，强调用纯函数、不可变数据和函数组合来构建程序，避免副作用。
    2. 高阶函数：接收函数作为参数或返回函数的函数。
    3. 纯函数：1. 相同输入 → 相同输出； 2. 不依赖外部状态； 3. 不修改外部变量。
19. 异步编程

    1. 概念：异步编程是指不会阻塞主线程执行的编程方式。
    2. 实现方式：1. 回调函数（callback）； 2. Promise； 3. Generator；4. async/await
20. js中继承【JS 的继承本质是基于原型链】

    1. 原型和原型链概念

       1. 原型：每个对象都有 `__proto__`​ 属性，它指向创建该对象的构造函数的 `prototype`，也就是指向它的原型。
       2. 原型链：当查找一个对象的属性时，JavaScript 会先在对象自身查找，如果找不到，就会沿着 `__proto__`​ 向上查找，直到找到或找到 `null`，这条链条即为原型链。
       3. 区别：`prototype`​ 是函数（构造函数）特有的，用于继承；`__proto__` 是所有对象都有的，用于指向原型链上游。
    2. 原型链继承：`Child.prototype = new Parent();`

       1. 优点：可以继承父类方法
       2. 缺点：父类引用类型属性会被共享
    3. 借用构造函数继承：`function Child() {   Parent.call(this); }`

       1. 优点：不共享引用类型
       2. 缺点：不能继承原型方法
    4. 组合继承：`Child.prototype = new Parent(); Child.prototype.constructor = Child;`

       1. 优点：
       2. 缺点：父类构造函数执行两次
    5. **寄生组合继承(** **最优解** **)** ：

       1. ```js
          function Parent() {
            this.name = 'parent';
          }

          function Child() {
            Parent.call(this);
          }

          Child.prototype = Object.create(Parent.prototype);
          Child.prototype.constructor = Child;
          ```
21. class 和 function 有什么区别？【class是构造函数的语法糖】

    1. 变量提升：funciton会提升，class不会
    2. 调用方式：class必须用new，function可作为函数使用，也可作为构造函数调用
    3. 继承机制：`class`​ 通过 `extends`​ 和 `super()`​ 实现了更直观的继承；而构造函数需要手动操作 `prototype`​ 和 `call/apply`。
    4. 静态方法：`class`​ 可以使用 `static`​ 关键字直接定义静态属性和方法；构造函数需要手动挂载到函数对象上（如 `Fn.staticMethod = ...`）
22. es6新特性

    1. let、const、symbol、map、set、proxy
    2. 箭头函数
    3. 解构赋值、扩展运算符、默认参数
    4. 模版字符串
    5. promise、class、async/await
    6. 模块化（import、export）
23. script（async、defer）

    1. defer：延迟执行，不阻塞页面，DOM 解析完毕，但在 `DOMContentLoaded` 事件之前执行，defer之间保持顺序执行。
    2. async：异步执行，不阻塞页面，加载完就执行，不保证顺序。
24. promise.any、promise.all、promise.race、promise.allSellted

    1. any：只要有一个resolve就成功，全部reject就失败
    2. all：全部都成功才fuifulled，只要有一个reject就失败
    3. race：第一个成功/失败的结果
    4. allSellted：不论成功/失败，最后返回全部的结果
25. Array.some、Array.every

    1. some：只要满足一个
    2. every：全部满足
26. for...in 和 for... of区别

    1. for...in：遍历对象和数组，
    2. for... of：遍历对象，
27. set、map、weakSet、weakMap

    1. set：集合，存唯一值。
    2. map：字典，键值对。
    3. weakSet：只能存放对象
    4. weakMap：只能存放对象
28. 数组和伪数组：

    1. **伪数组：**

       1. **含有length的普通对象，不能使用数组的方法。**
       2. **常见：**​`` document.querySelectorAll('div')` ``​、`arguments`
       3. 转数组：

          1. ​`Array.from(fakeArray)` (ES6推荐)
          2. ​`Array.prototype.slice.call(fakeArray)` (ES5常用)
          3. 扩展运算符: `[...fakeArray]`
29. js如何判空

    1. ​**基础/字符串/null/undefined**​：使用 `if (!value)` 判断假值。
    2. ​**空对象**   **​`{}`​** ​：使用 `Object.keys(obj).length === 0`。
    3. ​**空数组**   **​`[]`​** ​：使用 `arr.length === 0`。
    4. **字符串去空格**：使用 `str.trim().length === 0`。

# 进阶

1. 为什么 JS 是单线程？

   1. **JS 执行是单线程的，但浏览器不是单线程。**
   2. 主要是因为它要操作 DOM，而 DOM 不是线程安全的。如果是多线程，会产生数据竞争问题。
2. 进程和线程区别？

   1. 进程（一个运行的程序）：资源分配的最小单位；一个进程可以包含多个线程、不同进程之间内存是隔离的
   2. 线程（进程中的执行单元）：CPU 调度的最小单位；线程共享进程的内存空间
3. 浏览器是**多线程+多进程**

   1. 浏览器进程包括：

      1. 浏览器主进程
      2. 渲染进程（每个标签页一个）
      3. GPU 进程
      4. 网络进程
   2. 渲染进程内部是多线程

      1. JS 引擎线程（单线程执行 JS）
      2. GUI 渲染线程
      3. 事件线程
      4. 定时器线程
      5. 网络线程
4. 垃圾回收

   1. 概念：JS引擎自动释放不再使用的内存，防止内存泄漏。
   2. 引用计数：跟踪每个值被引用的次数。次数为0则回收。缺点是无法解决循环引用问题。
   3. 标记清除（主流算法）：从根对象（root）出发，标记所有能访问到的对象，未被标记的即为垃圾回收。
5. 内存泄露

   1. 概念：由于疏忽或代码错误，不再使用的内存未被垃圾回收机制释放，导致持续占用系统内存。
   2. 产生情况：

      1. ​**意外的全局变量**​：函数中未使用 `var/let/const`​ 定义的变量或使用 `this` 指向全局对象。
      2. ​**未清理的定时器/延时器**​：`setInterval`​ 或 `setTimeout` 引用的外部变量即使不再使用也无法释放。
      3. ​**闭包**：闭包维持了作用域链，若闭包被长期持有，其外部作用域变量无法释放。
      4. ​**脱离 DOM 的引用**：DOM 节点被移除，但在 JavaScript 变量中保留了对该节点的引用。
      5. ​**监听器未移除**​：`addEventListener`​ 绑定后未用 `removeEventListener` 清除，特别是单页应用（SPA）中组件销毁时。
      6. **闭包的错误使用**：函数内创建了大型对象，即使后续不需要，该闭包仍保持引用
