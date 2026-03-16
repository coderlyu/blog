---
title: VueJs总结
date: '2025-06-10 17:30:59'
head: []
outline: deep
sidebar: false
prev: false
next: false
---



# VueJs总结

![vue生命周期](./images)

# 基础

1. 对vue的理解，MVVM（M：model，V：view，VM：视图和逻辑双向绑定）

   1. **MVVM 与 MVC 的区别？**

      1. 侧重于 ViewModel 替代了 Controller，实现了数据与视图的自动同步，减少了 DOM 操作。
   2. **对Vue的理解**

      1. 一款用于构建用户界面的 JavaScript 框架，也是一个创建单页应用的Web应用框架。
      2. Vue 实现了基于 MVVM 的架构模式。在 Vue 中，**Model** 是 `data`​ 中的 JS 对象，**View** 是 `<template>`​ 定义的 DOM，**ViewModel** 是 Vue 实例本身。Vue 通过其特有的**响应式数据绑定机制**（Observer+Watcher），实现了数据的双向绑定：当数据变化时，视图会自动更新；当用户操作视图（如输入框），数据也会自动同步。这消除了手动 DOM 操作，实现了数据与视图的解耦
   3. **MVVM 模式的理解？**

      1. **Model** 是 `data`​ 中的 JS 对象，**View** 是 `<template>`​ 定义的 DOM，**ViewModel** 是 Vue 实例本身。Vue 通过其特有的**响应式数据绑定机制**（Observer+Watcher），实现了数据的双向绑定
   4. **Vue 中 Model、View 和 ViewModel 具体对应什么？**

      1. Model 是 JavaScript 数据对象（`data`​），View 是 DOM（模板），ViewModel 是 Vue 的实例（`vm`）。
2. 对SPA（单页应用）的理解

   1. 仅在 Web 页面初始化时加载相应的 HTML、JavaScript 和 CSS。一旦页面加载完成，页面不会因为用户的操作而进行重新加载或跳转，而是通过路由机制（如 `vue-router`）实现 HTML 内容的局部替换和数据交互。
   2. 缺点：

      1. 首屏加载慢（打包文件大）、SEO 不友好、前进后退路由管理复杂、初次渲染白屏时间较长
   3. 优点：

      1. 体验好、快（内容局部更新）、前后端分离、页面转场无刷新。
3. Vue2、Vue3生命周期

   1. **Vue2：**

      - beforeCreate
      - created
      - beforeMount
      - mounted
      - beforeUpdate
      - updated
      - activated
      - deactivated
      - beforeDestroy
      - destroyed
   2. vue2 Mixin：<span data-type="text" style="background-color: var(--b3-font-background7);">代码臃肿，难以维护</span>

      1. **不清晰的数据来源**
      2. **命名空间冲突**
      3. **隐式的跨 mixin 交流**
   3. **Vue3：（setup:：beforeCreate + created）**

      - onBeforeMount：组件被挂载之前被调用。
      - onMounted：组件挂载完成后执行（服务器端渲染期间不会被调用）
      - onBeforeUpdate：组件即将因为响应式状态变更而更新其 DOM 树之前调用。
      - onUpdated：组件因为响应式状态变更而更新其 DOM 树之后调用（服务器端渲染期间不会被调用）
      - onBeforeUnmount：组件实例被卸载之前调用（服务器端渲染期间不会被调用）。
      - onUnmounted：组件实例被卸载之后调用。
      - onErrorCaptured：在捕获了后代组件传递的错误时调用
      - onActivated：若组件实例是 [`&lt;KeepAlive&gt;`](https://cn.vuejs.org/api/built-in-components.html#keepalive) 缓存树的一部分，当组件被插入到 DOM 中时调用。
      - onDeactivated： 若组件实例是 [`&lt;KeepAlive&gt;`](https://cn.vuejs.org/api/built-in-components.html#keepalive) 缓存树的一部分，当组件从 DOM 中被移除时调用。
4. [透传attributes](https://cn.vuejs.org/guide/components/attrs)：

   1. “透传 attribute”指的是传递给一个组件，却没有被该组件声明为 [props](https://cn.vuejs.org/guide/components/props.html) 或 [emits](https://cn.vuejs.org/guide/components/events.html#defining-custom-events) 的 attribute 或者 `v-on` 事件监听器
   2. 当一个组件以单个元素为根作渲染时，透传的 attribute 会自动被添加到根元素上
5. vue3相比vue2有哪些改变

   1. **响应式系统的升级：从** **​`Object.defineProperty`​**​ **到** **​`Proxy`​**

      - ​`Proxy`​ 是代理整个对象，而 `defineProperty`​ 是递归遍历对象属性。因此 Vue3 在**大数据量对象初始化时的性能**会比 Vue2 好很多。
   2. **组合式 API (Composition API) 与选项式 API (Options API)**

      - 为什么？：Composition API 允许你将**同一个业务关注点的代码**（如搜索功能相关的响应式数据、方法、生命周期）聚合在一起，并封装成可复用的 `hooks`
   3. 生命周期变化

      - **命名变化：**  `beforeDestroy`​ / `destroyed`​ 更名为 `beforeUnmount`​ / `unmounted`，语义更准确。
      - **用法变化：**  Vue3 中，生命周期钩子需要在 `setup`​ 函数中调用（如 `onMounted(() => {})`​）。需要注意的是，`setup`​ 函数本身就是围绕 `beforeCreate`​ 和 `created` 生命周期运行的，所以这两个钩子被替代，无需显式定义。
   4. 渲染与性能优化

      - 编译模版优化，优化虚拟dom，标记静态节点；
      - 支持Tree-shaking，按需打包，体积更小
      - ​**​`v-if`​**​ **和** **​`v-for`​**​ **的优先级：** Vue2 中 `v-for`​ 优先级高于 `v-if`​；Vue3 中 `v-if`​ 优先级高于 `v-for`；
      - **Fragment (碎片) 支持：** Vue2 要求每个组件的 `template`​ 必须有一个唯一的根元素。Vue3 支持 **Fragment**，允许多个根节点，减少了不必要的 DOM 层级嵌套。
   5. 更好的typescript支持
6. vue2和vue3响应式的区别？

   1. vue2

      1. 基于 `Object.defineProperty` 遍历数据对象的所有属性，通过 getter/setter 监听数据变化，并在 dep 中收集依赖。
      2. 数组的处理：Vue2 对数组的 `push`​, `pop`​, `shift`​, `unshift`​, `splice`​, `sort`​, `reverse` 七个方法进行了重写（劫持），以实现数组数据变化时更新视图。
      3. 瓶颈：主要是初始化时的递归遍历对象深层属性，即使此时数据没有被渲染使用，这也消耗大量内存和 CPU。
   2. vue3

      1. 通过 Proxy 代理目标对象，在 getter 中进行 `track`​（依赖收集），在 setter 中进行 `trigger`（触发更新），基于 WeakMap 保存依赖关系。
      2. **[Proxy 相比 defineProperty 有什么优势？](https://www.google.com/search?q=Proxy+%E7%9B%B8%E6%AF%94+defineProperty+%E6%9C%89%E4%BB%80%E4%B9%88%E4%BC%98%E5%8A%BF%EF%BC%9F&sca_esv=0ff7534cf1487ec7&biw=1601&bih=898&sxsrf=ANbL-n5qSp199DzUeshcfTTUTVXXdpNy9A%3A1772855105513&ei=QZ-raYqGH4jQ2roP0KaHkAE&ved=2ahUKEwi8066m442TAxUUsVYBHXkGKYQQgK4QegQIBhAE&uact=5&oq=vue2%E5%92%8Cvue3%E5%93%8D%E5%BA%94%E5%BC%8F%E9%9D%A2%E8%AF%95%E9%A2%98%E9%97%AE%E4%BB%80%E4%B9%88&gs_lp=Egxnd3Mtd2l6LXNlcnAiJnZ1ZTLlkox2dWUz5ZON5bqU5byP6Z2i6K-V6aKY6Zeu5LuA5LmIMgUQABjvBTIFEAAY7wUyCBAAGKIEGIkFMgUQABjvBUiqkAFQ6QZY_o4BcAh4AJABAZgB8wOgAbQwqgEKMS4yOC4zLjMuMbgBA8gBAPgBAZgCJ6AC3SWoAgHCAggQABiwAxjvBcICBhCzARiFBMICChAAGIAEGEMYigXCAggQABiABBixA8ICCxAAGIAEGLEDGIMBwgIREC4YgAQYsQMY0QMYgwEYxwHCAhAQLhiABBjRAxhDGMcBGIoFwgIFEAAYgATCAggQABiABBiiBMICCRAhGKABGAoYKsICBxAhGKABGAqYAwPxBXqNE33dvWTBiAYBkAYFkgcIOS4yNi4yLjKgB81hsgcIMS4yNi4yLjK4B8AlwgcHMS4yNS4xM8gHYoAIAA&sclient=gws-wiz-serp&mstk=AUtExfCQeaUAulnIBE_XkeJwamL5jTyUasxvp8cC8yIUk9w0FF9sFYKzy08V-FHJ_wgqnoVd0NLFa9yJQhO__T9GuHwKKLzBw06Bd18cW-mWwXPWIkZ67JKV-hF1V0wIJ1L3dDSeAyCzPWDsWn6LSizBEgwxoOgxQzeyH0zeocp4b19KHdA&csui=3)**

         1. 可以原生监听数组变化（无需像Vue2那样重写方法）。
         2. 可以劫持新增、删除属性的操作。
         3. 惰性监听，只有在访问到属性时才会递归，性能更好。
7. ref和reactive区别

   1. ​**数据类型**​：`ref`​支持任何类型（基本类型如字符串、数字，以及对象/数组）；`reactive`仅支持引用类型（对象、数组）。
   2. ​**访问方式**​：`ref`​在JS中必须通过`.value`​访问/修改，模板中不需要；`reactive`​不需要`.value`。
   3. ​**实现原理**​：`ref`​通过包装成包含`.value`​的包裹对象实现；`reactive`​通过`Proxy`实现。
   4. ​**响应式丢失**​：`ref`​在解构时可以配合`toRefs`​保持响应性；`reactive`直接解构会失去响应性。
   5. ​**赋值操作**​：`ref`​可以直接重新赋值（如`refData.value = {新对象}`​）；`reactive`不能直接重新赋值整个对象，否则会断开响应。
8. v-if和v-for为什么不一起使用：浪费性能，如果v-for数据很大，v-if过滤掉了大部分，在vue2中仍然会循环整个列表

   1. vue2中： v-for优先级高，
   2. vue3中：v-if优先级高
9. spa首屏优化（看`performance`）

   1. 减少入口文件体积（code-split）
   2. 资源缓存：强缓存（`Cache-Control`​），协商缓存（`Last-Modified`​，`Etag`）
   3. 资源按需加载（import），使用cdn
   4. 开启GZIP压缩
   5. 使用SSR服务端渲染
10. 响应式的原理

    1. vue2: `Object.defineProperty`​劫持对象的属性， `get`​收集依赖， `set`通知更新，用发布订阅模式+观察者模式响应式地实现

       1. 发布订阅模式：收集依赖，注册监听器
       2. 观察者模式：存储修改数据和修改dom数据的能力
       3. ```js
          data -> Observer -> defineProperty -> getter/setter
                  ↓                     ↑
               Watcher <---- Dep（依赖收集/派发更新）
          ```

8. v-if和v-show区别：

   1. v-show：生成全部节点，然后判断条件隐藏节点（display: none）
   2. v-if：则在条件为false的时候，不生成节点，dom上直接无节点
9. 观察者模式和发布订阅模式的区别：

   1. 观察者模式：数据变化，自动通知依赖他的观察者（一对多）
   2. 发布订阅模式：发布者发出消息 → 所有订阅者接收处理消息（多对多）
10. data为什么是一个函数：根实例对象可以是函数和对象，但是组件必须是函数（防止多个组件共享同一份data对象）
11. 模版编译原理：模版编译（解析ast，优化，生成） -> 渲染函数（render） -> 虚拟元素（VNode） -> 真实dom（patch）

    1. <span data-type="text" style="background-color: var(--b3-font-background12);">Vue 会把模板编译成渲染函数，执行后生成虚拟 DOM，再通过 diff 算法将变化同步到真实 DOM，这样实现了响应式和高性能更新。Vue 3 编译器也更灵活、支持 tree-shaking 与静态提升。</span>
12. vue3静态提升（提升diff性能）：找出静态节点（纯文本、纯属性），这些静态节点用变量保存到 `const hoisted_1 = h('div', {...})`​，在 `render()` 函数中直接复用这些变量，而不是重新生成节点
13. diff算法

    1. vue2:

       1. 同层比较
       2. 循环从两边向中间比较<span data-type="text" style="background-color: var(--b3-font-background1);">【双端指针】（</span>`头头比`​​​​​<span data-type="text" style="background-color: var(--b3-font-background1);">、</span>`头尾比`​​​​​<span data-type="text" style="background-color: var(--b3-font-background1);">、</span>`尾头比`​​​​​<span data-type="text" style="background-color: var(--b3-font-background1);">、</span>`尾尾比`​​​​​<span data-type="text" style="background-color: var(--b3-font-background1);">）</span>
    2. vue3:

       1. 通过编译阶段分析动态内容和静态标记，
       2. Vue3 子节点 diff 采用了优化版的 `最长递增子序列（LIS）`​ 算法来**最小化 DOM 移动操作数量**，性能提升明显。
14. vue3中 `PatchFlag` 是什么

    1. Vue3 的编译器（template compiler）会分析模板中哪些部分是**静态的**，哪些是**动态绑定的属性、事件、插槽等**。
    2. <span data-type="text" style="background-color: var(--b3-font-background1);">每一个动态属性会对应一个 PatchFlag 常量（其实是位运算掩码）; 渲染时，通过 PatchFlag 快速判断需要更新什么，不需要更新什么</span>
15. 组件间通讯

    1. 父子组件：**[Props & \$emit](https://www.google.com/search?q=Props+%26+%24emit&sca_esv=0ff7534cf1487ec7&biw=1601&bih=898&sxsrf=ANbL-n6uPOZHa_oTaQEtYCCUdeZkflU4dg%3A1772886291107&ei=ExmsaYGbBsXb2roPt-CVwAE&ved=2ahUKEwiBleGq5o2TAxXZlFYBHYDZDdoQgK4QegQIBBAB&uact=5&oq=Vue+%E7%BB%84%E4%BB%B6%E9%97%B4%E9%80%9A%E8%AE%AF%E6%96%B9%E5%BC%8F&gs_lp=Egxnd3Mtd2l6LXNlcnAiGVZ1ZSDnu4Tku7bpl7TpgJrorq_mlrnlvI8yCRAhGKABGAoYKjIHECEYoAEYCkiSLlCyAlj_LHABeAGQAQCYAccBoAHoHqoBBDEuMjm4AQPIAQD4AQGYAh2gAq4dwgIKEAAYsAMY1gQYR8ICChAAGIAEGEMYigXCAg0QABiABBixAxhDGIoFwgIFEAAYgATCAgcQABiABBgMwgIHEAAYgAQYCsICBRAAGO8FwgIFECEYoAGYAwCIBgGQBgqSBwYxLjI3LjGgB95HsgcGMC4yNy4xuAelHcIHBzAuMTYuMTPIB2CACAA&sclient=gws-wiz-serp&mstk=AUtExfBsGVE2hRUaC7aChg8mEvmLO-qH8FuIvqe3gjQblTbugq1seO6WGoS6HSyc67hckKKZvFCplzIsglh5HRAQFq6SiDizNqi3clGwdfHUIFaJgBbuPIihcOuyVu353U7FHkbK3GxWqaWuDfhq4P6ftGi7Pe2nccfA4y9DnhXfkCFht5GPUEyUVbZ2vYpsh2R246Sgowz3KBe8EvAurXZ1SP7Qet9XkliJ7bdyoQprO2x0pBrf-5K10VnUNFBxb8cXgA87KEtVwFiwml8JiD9zncffGUJZShPlqmA179C0aGCUlJANjgulZE8Bomw7QWJ7Bzg37vbZF-JJjAzagXQ74AhYRz7QWSe4bY-pkOUN-UZyftnEu3tvXgE5vg-qzoILmU67SHg8QkWxo30pjSMkYA&csui=3)**
    2. 兄弟组件：将数据放在共同父组件上，通过**[Props & \$emit](https://www.google.com/search?q=Props+%26+%24emit&sca_esv=0ff7534cf1487ec7&biw=1601&bih=898&sxsrf=ANbL-n6uPOZHa_oTaQEtYCCUdeZkflU4dg%3A1772886291107&ei=ExmsaYGbBsXb2roPt-CVwAE&ved=2ahUKEwiBleGq5o2TAxXZlFYBHYDZDdoQgK4QegQIBBAB&uact=5&oq=Vue+%E7%BB%84%E4%BB%B6%E9%97%B4%E9%80%9A%E8%AE%AF%E6%96%B9%E5%BC%8F&gs_lp=Egxnd3Mtd2l6LXNlcnAiGVZ1ZSDnu4Tku7bpl7TpgJrorq_mlrnlvI8yCRAhGKABGAoYKjIHECEYoAEYCkiSLlCyAlj_LHABeAGQAQCYAccBoAHoHqoBBDEuMjm4AQPIAQD4AQGYAh2gAq4dwgIKEAAYsAMY1gQYR8ICChAAGIAEGEMYigXCAg0QABiABBixAxhDGIoFwgIFEAAYgATCAgcQABiABBgMwgIHEAAYgAQYCsICBRAAGO8FwgIFECEYoAGYAwCIBgGQBgqSBwYxLjI3LjGgB95HsgcGMC4yNy4xuAelHcIHBzAuMTYuMTPIB2CACAA&sclient=gws-wiz-serp&mstk=AUtExfBsGVE2hRUaC7aChg8mEvmLO-qH8FuIvqe3gjQblTbugq1seO6WGoS6HSyc67hckKKZvFCplzIsglh5HRAQFq6SiDizNqi3clGwdfHUIFaJgBbuPIihcOuyVu353U7FHkbK3GxWqaWuDfhq4P6ftGi7Pe2nccfA4y9DnhXfkCFht5GPUEyUVbZ2vYpsh2R246Sgowz3KBe8EvAurXZ1SP7Qet9XkliJ7bdyoQprO2x0pBrf-5K10VnUNFBxb8cXgA87KEtVwFiwml8JiD9zncffGUJZShPlqmA179C0aGCUlJANjgulZE8Bomw7QWJ7Bzg37vbZF-JJjAzagXQ74AhYRz7QWSe4bY-pkOUN-UZyftnEu3tvXgE5vg-qzoILmU67SHg8QkWxo30pjSMkYA&csui=3)**
    3. 跨页面：

       1. **[Provide / Inject](https://www.google.com/search?q=Provide+%2F+Inject&sca_esv=0ff7534cf1487ec7&biw=1601&bih=898&sxsrf=ANbL-n6uPOZHa_oTaQEtYCCUdeZkflU4dg%3A1772886291107&ei=ExmsaYGbBsXb2roPt-CVwAE&ved=2ahUKEwiBleGq5o2TAxXZlFYBHYDZDdoQgK4QegQICBAB&uact=5&oq=Vue+%E7%BB%84%E4%BB%B6%E9%97%B4%E9%80%9A%E8%AE%AF%E6%96%B9%E5%BC%8F&gs_lp=Egxnd3Mtd2l6LXNlcnAiGVZ1ZSDnu4Tku7bpl7TpgJrorq_mlrnlvI8yCRAhGKABGAoYKjIHECEYoAEYCkiSLlCyAlj_LHABeAGQAQCYAccBoAHoHqoBBDEuMjm4AQPIAQD4AQGYAh2gAq4dwgIKEAAYsAMY1gQYR8ICChAAGIAEGEMYigXCAg0QABiABBixAxhDGIoFwgIFEAAYgATCAgcQABiABBgMwgIHEAAYgAQYCsICBRAAGO8FwgIFECEYoAGYAwCIBgGQBgqSBwYxLjI3LjGgB95HsgcGMC4yNy4xuAelHcIHBzAuMTYuMTPIB2CACAA&sclient=gws-wiz-serp&mstk=AUtExfBsGVE2hRUaC7aChg8mEvmLO-qH8FuIvqe3gjQblTbugq1seO6WGoS6HSyc67hckKKZvFCplzIsglh5HRAQFq6SiDizNqi3clGwdfHUIFaJgBbuPIihcOuyVu353U7FHkbK3GxWqaWuDfhq4P6ftGi7Pe2nccfA4y9DnhXfkCFht5GPUEyUVbZ2vYpsh2R246Sgowz3KBe8EvAurXZ1SP7Qet9XkliJ7bdyoQprO2x0pBrf-5K10VnUNFBxb8cXgA87KEtVwFiwml8JiD9zncffGUJZShPlqmA179C0aGCUlJANjgulZE8Bomw7QWJ7Bzg37vbZF-JJjAzagXQ74AhYRz7QWSe4bY-pkOUN-UZyftnEu3tvXgE5vg-qzoILmU67SHg8QkWxo30pjSMkYA&csui=3)**
       2. pinia
16. nextTick的理解（vue是异步更新dom的，如果要获取到最新的dom信息，可以在nextTIck回调中获取）

    1. DOM更新完成后执行的回调函数，
    2. 底层是用微任务队列（同一事件多次nextTick会合并）
17. slot（默认插槽，具名插槽， 作用域插槽）

    1. 概念：是Web组件内的一个占位符，该占位符可以在后期使用自己的标记语言填充
    2. 默认插槽：只有一个，没有名字。
    3. 具名插槽：使用 `v-slot:name`​ 或 `#name` 绑定，允许多个插槽。
    4. 作用域插槽：父组件通过 `v-slot:name="slotProps"`​ 获取子组件 `slot` 标签上绑定的数据。
18. key的作用：key给虚拟dom中节点的唯一标识，在dom diff对比时提高性能
19. 事件修饰符

    1. .stop：`stopPropagation` 阻止捕获和冒泡阶段中当前事件的进一步传播（不能防止任何默认行为的发生）
    2. .prevent：`preventDefault` 阻止默认行为（例如页面滚动、链接跳转或粘贴文本）
    3. .self：仅当 event.target 是元素本身时才会触发事件处理器
    4. .once：只触发一次，再次点击不再触发。
    5. .passive：**不阻止**默认行为（例如页面滚动、链接跳转或粘贴文本）。
    6. .capture：监听捕获阶段（事件分冒泡阶段【从里到外传递】和捕获阶段【从外到里传递】）。
20. 按键修饰符

    1. .enter: input框键入回车键时触发
    2. .tab:
    3. .delete: 捕获“Delete”和“Backspace”两个按键
    4. .right
    5. .left
21. hash路由和history路由：

    1. hash路由： `onhashChange`
    2. history路由：`history.pushState()`​和`history.replaceState()`。
22. watch和computed区别：

    1. watch：用来侦听某个变化，没有返回值，不缓存结果，有变化就执行（<span data-type="text" style="background-color: var(--b3-font-background1);">懒执行，变化才触发， watchEffect会立即执行一次，收集依赖</span>）
    2. computed：计算属性，有返回值，会缓存结果，依赖不变不更新。
23. keep-alive：组件切换过程中将状态保存到内存中（缓存不活动的组件实例），防止重复渲染dom

    1. activated和deactivated：

       - <span data-type="text" style="background-color: var(--b3-font-background2);">首次进入组件时：</span>`beforeRouteEnter`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; </span>`beforeCreate`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; </span>`created`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);">&gt; </span>`mounted`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; </span>`activated`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; ... ... &gt; </span>`beforeRouteLeave`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; </span>`deactivated`​
       - <span data-type="text" style="background-color: var(--b3-font-background2);">再次进入组件时：</span>`beforeRouteEnter`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt;</span>`activated`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; ... ... &gt; </span>`beforeRouteLeave`​​​​​<span data-type="text" style="background-color: var(--b3-font-background2);"> &gt; </span>`deactivated`​
24. SEO优化（搜索引擎优先爬取页面HTML结构）

    1. SEO概念：是一种通过优化网站内容、结构和技术细节，从而在搜索引擎（如Google、百度）的自然搜索结果中获得更高排名、增加曝光度和吸引更多免费流量的系统性营销方法。
    2. Vue SEO怎么做：

       1. **SSR（服务端渲染）：**  使用Nuxt.js或Vue SSR将组件在服务端渲染为HTML字符串发送给浏览器，利于SEO且首屏加载快。
       2. **预渲染（Prerender）：**  对于路由较少的静态网站，使用 `prerender-spa-plugin` 在构建时生成静态HTML文件。
       3. 标签语义化，正确的标签做正确的事，优化页面结构
       4. 管理页面的title和meta
       5. 高质量反向链接
25. 前端权限怎么做（接口权限，按钮权限，菜单权限，路由权限）

    1. 路由权限：[动态路由](https://router.vuejs.org/zh/guide/advanced/dynamic-routing#%E5%8A%A8%E6%80%81%E8%B7%AF%E7%94%B1)，用户登录后，后端返回权限标识数组（如 `['user:add', 'order:view']`​）。前端在路由守卫中过滤出有权限的路由，使用 `router.addRoute` 动态挂载。
    2. 菜单权限：根据过滤后的路由表生成左侧菜单。
    3. 按钮权限：使用 `v-if="hasPermission('user:add')"`
    4. 接口权限：由后端中间件判断
26. [解决跨域：JSONP，CORS，代理](https://cloud.tencent.com/developer/article/2132990)

    1. **跨域概念：**​**浏览器****的限制策略，即协议、域名、端口任意一个不同即为跨域。**
    2. JSONP：**当需要跨域请求时，不使用AJAX，转而生成一个script元素去请求服务器，由于浏览器并不阻止script元素的请求，这样请求可以到达服务器。服务器拿到请求后，响应一段JS代码，这段代码实际上是一个函数调用，调用的是客户端预先生成好的函数，并把浏览器需要的数据作为参数传递到函数中，从而间接的把数据传递给客户端**
    3. CORS：需要服务器配置Access-Control-Allow-Origin，允许跨域请求
    4. 代理：开发环境下，本地开启代理服务器
27. **组件 v-model（**​**[defineModel](https://cn.vuejs.org/guide/components/v-model.html)**​ **）**

    1. ​`v-model` 可以在组件上使用以实现双向绑定。
    2. ​`defineModel()` 返回的是ref
    3. 底层机制

       - 一个名为 `modelValue` 的 prop，本地 ref 的值与其同步；
       - 一个名为 `update:modelValue` 的事件，当本地 ref 的值发生变更时触发。
       - ```js
         // 子组件
         <template>
           <input :value="props.description" @input="emit('update:description', $event.target.value)" />
         </template>
         <script lang="ts" setup>
         const props = defineProps(["description"]);
         const emit = defineEmits(["update:description"]);
         </script>


         // 父级组件
         <Description v-model:description="user.description" />
         ```
28. [watch 和 watchEffect](https://cn.vuejs.org/guide/essentials/watchers.html#watch-vs-watcheffect)

    1. watch：懒执行，仅当数据源变化时，才会执行回调（可指定 `immediate: true`）

       - 可监听：ref、reactive、函数返回值（getter）、一个包含以上的数组
    2. watchEffect：回调立即执行。

## 进阶

‍

1. vue2和vue3响应式原理对比

   1. |特性|Vue2 (`Object.defineProperty`)|Vue3 (`Proxy`)|
      | ------| ----------------------------------------| -----------------------------------------------|
      |**底层 API**|​`Object.defineProperty`|​`Proxy`|
      |**响应式粒度**|属性级别（需递归）|对象级别（无需递归）|
      |**对象新增/删除属性**|​`Vue.set()`​/`Vue.delete()`|直接添加/删除即可响应|
      |**数组响应式支持**|重写 7 个数组变异方法（如`push`​、`splice`）|完整支持所有数组操作|
      |**深层嵌套监听**|必须递归所有属性，初始化成本高|懒监听，访问时才代理，性能更优|
      |**性能**|初始化阶段性能差，且多对象占内存|更快更省资源，尤其在大数据场景中表现好|
      |**原始类型支持**|不支持包装原始类型响应式|支持原始值响应式（`ref(1)`）|
      |**可扩展性**|不可代理新增属性、Map、Set、WeakMap 等|支持所有类型：对象、Map、Set、WeakMap、数组等|
      |**兼容性**|IE9+ 支持|不支持 IE（Proxy 不兼容）|
2. vue2和vue3区别（<span data-type="text" style="background-color: var(--b3-font-background7);">响应式原理、性能优化、语法增强、TypeScript 支持、组件架构</span>）

   1. 双向数据绑定原理不同：vue2：  `Object.definePrototype`​， vue3: `Proxy`
   2. vue3支持 **Fragments，即可以拥有多个根节点。**
   3. vue2是options API，vue3是compositon API（好处是： 相同功能的变量统一管理，方便维护）
   4. 生命周期函数变化

      1. vue2:

         - beforeCreate 组件创建之前

         - created 组件创建之后
         - beforeMount 组价挂载到页面之前执行
         - mounted 组件挂载到页面之后执行
         - beforeUpdate 组件更新之前
         - updated 组件更新之后
      2. vue3:

         - setup 开始创建组件
         - onBeforeMount 组价挂载到页面之前执行
         - onMounted 组件挂载到页面之后执行
         - onBeforeUpdate 组件更新之前
         - onUpdated 组件更新之后
   5. 性能优化：vue3静态节点提升，diff算法优化
   6. vue3更有利有tree-shaking
3. vite为什么快（开发时用esbuild， 生产环境用rollup， esbuild速度快）

   1. 浏览器原生ESM特性, `<script type="module" src="1.js">`​，`1.js`​文件中可以正常识别 `import`​和 `export, export default`
   2. 本地开发时，对浏览器请求本地文件，进行按需编译
   3. 启动时，对node_modules进行打包（依赖优化）
4. vue双向绑定原理（<span data-type="text" style="background-color: var(--b3-font-background7);">定义-&gt;原理-&gt;语法糖-&gt;应用场景</span>）：（v-model和数据劫持原理【vue2的Object.defineProperty 或Vue3的 Proxy】）

   1. **定义：**

      - Vue的双向绑定是指：数据模型（Model）的变化能自动驱动视图（View）更新，同时在视图中的交互（例输入）也能实时改变数据模型，在Vue中我们通常使用 `v-model` 指令在表单上实现这种绑定。
   2. **原理（其底层基于数据响应式系统）** ：

      - Vue2

        - 采用 `Object.defineProperty` 将对象的属性转换为 getter/setter。当读取数据时收集依赖（Watcher），修改数据时通过发布订阅模式（Dep）通知视图更新。
      - Vue3

        - 使用 ES6 的 `Proxy` 代理对象，性能更强且能监测到数组下标和对象新增属性的变化。
   3. **语法糖**：

      1. ​`v-model`​ 其实是语法糖。在原生表单组件上，它默认相当于 `:value="msg"`​ 和 `@input="msg = $event.target.value"`​ 的结合。对于自定义组件，它默认绑定名为 `value`​ 的 prop 和名为 `input` 的事件。
   4. **场景**：

      1. 表单提交、实时搜索、数据编辑。
5. 模板编译（ **​`<template>`​** ​**转换为浏览器可执行的**​**​`render`​**​**函数**）：**解析AST ->**  **优化静态节点 ->**  **生成render函数**

   1. **解析AST：** 将模板字符串解析成 AST（抽象语法树）。
   2. **优化静态节点：** 遍历 AST，标记静态节点（即永远不会变的数据），从而在 Diff 时跳过它们，提高渲染效率。
   3. **生成render函数：** 将优化后的 AST 转换成 `render` 函数代码字符串。
6. 为什么Vue需要模板编译？

   - 因为浏览器无法直接理解带有指令、插值语法的Vue模板，必须将模板转换为渲染页面结构的JavaScript函数。
7. 什么是AST（抽象语法树）？

   - 用JS对象的形式来描述HTML结构，例如标签、属性、文本内容。
8. Vue 3相对于Vue 2的模板编译做了哪些优化？

   - **Patch Flag：**  标记节点动态属性，Diff时只比对这些变化的内容。
   - **Hoisting（静态提升）：**  将静态节点提升到渲染函数之外，避免重复创建。
   - **Cache Handles：**  缓存事件处理函数。
9. 在生产环境中使用runtime-only和runtime-compiler有什么区别？

   - ​`runtime-only`：不包含编译器，代码体积更小，速度更快，需要在构建时提前编译模板。
   - ​`runtime-compiler`：包含编译器，支持在客户端运行时编译模板。
10. 首屏优化

    1. 核心手段：压缩、懒加载、服务端渲染。
    2. 核心策略：

       1. **减少体积：**  路由懒加载、组件异步导入、UI库按需引入、第三方库CDN引入。
       2. **加快速度：**  开启Gzip压缩、开启HTTP/2、CDN静态资源缓存。
       3. **体验优化：**  骨架屏、Loading加载图标。
       4. **架构优化：**  如果首屏非常重要且数据依赖后端，考虑SSR。
11. 运行时（Runtime）和编译时（Compiler）有什么区别？

    1. **编译时（Compiler）**

       - 主要考察 `.vue` 文件如何转译为浏览器可识别的 JS，以及 Vue 如何在编译期预判代码变化。
    2. **运行时（Runtime）** 

       - 主要考察 `render` 函数执行、Virtual DOM、Patch 算法和响应式系统。
12. **Vue3 的渲染性能为什么比 Vue2 快？**

    1. 基于 Proxy 的响应式系统，Proxy 直接代理对象无需深层递归；
    2. 运行时配合编译时优化的静态标记，减少了对比不必要的节点。
13. **Virtual DOM 的原理是什么？**

    1. 运行时通过 JS 对象描述界面结构，在数据变更后生成新旧 VNode，通过 Diff 算法计算最小变化，从而更新真实 DOM。
14. **Virtual DOM 的优势有哪些？**

    1. 性能提升：避免直接操作真实DOM产生的重排重绘，通过diff算法局部更新提升性能
    2. 跨平台：：虚拟DOM抹平了平台差异，**使Vue可以渲染到Web、移动端（Weex）等**
    3. 数据驱动：开发者只需修改数据，Vue通过组件化机制自动完成DOM的更新，开发者专注于业务逻辑。
15. **虚拟DOM的diff算法（对比过程）是怎样的？**

    1. 同级比较，深度遍历子元素对比
    2. Vue通过新旧两棵虚拟DOM树进行同层级比较（patch）。它采用深度优先遍历，对比节点的标签、属性、文本内容，并结合Key值，找出需要修改的最小差异，最后应用到真实DOM上。

‍
