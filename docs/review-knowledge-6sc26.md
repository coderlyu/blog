---
title: 复习知识
date: '2026-03-07 10:59:30'
head: []
outline: deep
sidebar: false
prev: false
next: false
---



# 复习知识

1. HTML知识知识总结[^1]
2. CSS知识知识总结[^2]
3. JavaScript知识知识总结[^3]
4. Webpack知识Webpack知识总结[^5]
5. Vue知识知识总结[^6]
6. 笔试部分笔试题[^7]
7. 计算机网络知识总结[^8]
8. 算法
9. 基建前端基建[^9]

‍

# 面试题

1. [前端常见面试题总结](https://q.shanyue.tech/fe)
2. [前端知识库](https://adjfks.github.io/daydayup-website/Interview/CSS.html#%F0%9F%91%80%E5%9F%BA%E7%A1%80)

‍

[^1]: # 知识总结

    # 基础

    1. html5新特性

       1. 语义化标签：`<header>`​, `<footer>`​, `<nav>`​, `<section>`​, `<article>`​, `<aside>`。
       2. 本地存储：`localStorage`​（永久）、`sessionStorage`（会话结束即消失）。
       3. 多媒体：`<video>`​（视频）、`<audio>`（音频）。
       4. 绘图：`<canvas>`元素。
       5. 表单增强：`input`​类型如 `type="date"`​, `email`​, `url`​, `range` 等。
       6. 其他：地理定位（Geolocation）、拖拽（Drag and Drop）、Web Workers、WebSocket。
    2. html语义化理解

       1. 概念：用正确的标签做正确的事，使代码结构清晰、内容易读。
       2. 优势：

          1. **可维护性/可读性：**  开发者无需深入阅读代码即可理解结构。
          2. **SEO（搜索引擎优化）：**  搜索引擎爬虫更容易理解内容结构，有助于提高排名。
          3. **[无障碍性（Accessibility）](https://developer.mozilla.org/zh-CN/docs/Learn_web_development/Core/Accessibility/HTML)**​ **：**  屏幕阅读器可根据语义读出内容，对残障人士友好。

             1. ​**屏幕阅读器友好（语义化DOM）** ​：辅助技术读取 `<header>`​, `<nav>`​, `<main>`​, `<footer>`​ 等语义化标签时，能自动识别页面结构（页眉、导航、主内容、页脚），帮助盲人用户快速定位和导航，而不是面对一片混乱的 `<div>`。
             2. ​**交互控件的无障碍**​：使用 `button`​ 而不是 `div`​ 做按钮，`<button>` 自动获得Tab键聚焦、Enter/Space键触发功能，无需额外编码即可满足键盘操作习惯。
             3. ​**文字等效内容**​：通过 `<img>`​ 标签的 `alt` 属性为图片提供文字描述，让屏幕阅读器用户能“听到”图片内容。
             4. ​**表单和标记**​：使用 `<label>`​ 绑定 `<input>` 控件，使得屏幕阅读器在聚焦输入框时能读出相对应的文字提示，且点击标签文本也能选中输入框，提高认知障碍和视障人士的交互效率。
             5. ​**增强结构逻辑**​：使用 `<h1>`​-`<h6>` 标题层级，使盲人用户能迅速理解页面层级结构，而非仅依赖字体大小。
       3. **常用语义化标签：**  熟练说出 `<header>`​（头部）、`<footer>`​（底部）、`<nav>`​（导航）、`<article>`​（独立文章）、`<section>`​（章节）、`<aside>`​（侧边栏）、`<main>`（主内容）等。
    3. ​ **​`<!DOCTYPE>`​** 是干嘛的，有哪些属性

       1. 概念：它是一种文档类型声明（DTD），告诉浏览器解析器用什么文档类型定义来解析文档。
       2. 主要作用：触发浏览器的标准模式（Standards Mode），确保不同浏览器以相同标准渲染页面。
       3. **标准模式与混杂模式（Quirks Mode）的区别？**

          - **标准模式：**  浏览器按照 W3C 标准解析和渲染页面。
          - **混杂模式：**  浏览器以宽松的、向后兼容的方式解析页面，通常兼容旧版本 IE 的行为。
       4. **如果不写**  **​`<!DOCTYPE>`​** ​ **会怎么样？**

          - **回答：**  会触发浏览器的​**混杂模式（Quirks Mode）** 。此时，浏览器会模拟老版本浏览器的行为（向后兼容）处理页面，这可能导致 CSS 渲染差异，即所谓的“怪异模式”。
    4. ​`<meta>` 标签是干什么的，都有什么属性和作用

       1. 概念：位于 `<head>` 内部，不显示在页面上，向浏览器、搜索引擎等机器提供页面元信息（如字符编码、SEO、viewport），有利于SEO优化和渲染控制。
       2. 常用属性

          1. name：描述的是网页文档的信息（例如：作者、⽇期和时间、⽹⻚描述、 关键词）

             1. keywords：设置网页关键词 (SEO)；`<meta name="keywords" content="电商,好货,便宜">`
             2. viewport：设置网页视口（viewport）控制视⼝的⼤⼩、缩放和⽐例等 (移动端开发)；`<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">`
             3. ​`description`：一段简短而精确的、对页面内容的描述。一些浏览器，比如 Firefox 和 Opera，将其用作书签的默认描述。
          2. http-equiv：描述的相当于是 HTTP 响应头信息（例如：网页内容信息, 网页缓存等）

             1. 设置 http 响应头：Content-Type 网页内容类型 (字符集)；`<meta http-equiv="content-type" content="text/html;charset=utf-8">`
          3. content：此属性包含 [`http-equiv`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/meta#http-equiv)​ 或 [`name`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/meta#name) 属性的值，具体取决于所使用的值。
          4. charset：字符集声明，告诉文档使用哪种字符编码

             1. ​`<meta charset="utf-8">`
          5. [itemprop](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Global_attributes#itemprop)：提供用户定义的元数据
    5. [img ](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/img)​[`srcset`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/img)​[有什么用？](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/img)

       1. 处理响应式图片的方式 (css媒体查询换的是背景图片, 而不是 img 标签的 src) 开发者和设计师们竞相寻求 处理响应式图片的方法。
       2. ​`<img srcset="320.png 1x, 640.png 2x, 960.png 3x" />`
    6. **Iframe**

       1. 概念：在一个html页面中嵌入另一个html页面。
       2. 优点：

          1. 加载第三方内容：如广告、视频、地图等，避免第三方代码阻塞主页面渲染。
          2. 独立性：嵌入的页面与原页面隔离，互不干扰，可实现内容独立加载。
          3. 代码复用：多个页面可共用一个 iframe 内容（如头部/底部），方便维护。
       3. 缺点：

          1. ​**性能问题**​： iframe 会阻塞主页面的 `Onload` 事件，且每个 iframe 都会创建一个新的浏览器上下文，占用内存和连接。
          2. ​**SEO 问题**：搜索引擎爬虫对 iframe 的内容抓取不够友好。
          3. ​**安全性**：易受到跨站脚本攻击（XSS）。
          4. **布局问题**： iframe 样式调整和高度自适应较为麻烦。
       4. 通讯

          1. **同源下通信**：父页面可以通过 `iframeElement.contentWindow`​ 获取子窗口的 `window`​ 对象，子页面通过 `window.parent` 获取父窗口对象。
          2. **跨域通信**：使用 **​`window.postMessage`​**​ 机制。这是面试最常考的方法，涉及 `postMessage(data, origin)`​ 发送和 `message` 事件监听。
       5. 安全

          1. ​**​``​**​ **[属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Reference/Elements/iframe#sandbox)**：面试中必问。用于限制 iframe 的能力，例如 `<iframe sandbox="allow-scripts allow-forms allow-same-origin">`，可以禁用脚本、表单提交等，以增强安全性。
          2. ​**​``​**​ **[(Content Security Policy)](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Guides/CSP)** ：使用 `Content-Security-Policy` 响应头限制哪些域名可以嵌入为 iframe。
    7. **src vs href**

       1. ​**​`src`​**​  **(Source):**

          1. **用于替换当前元素（嵌入资源），会阻塞文档解析；**
          2. 指向外部资源的位置，该资源会被下载并嵌入到文档中当前标签所在的位置。它替换了当前元素。常见于 `<img>`​、`<script>`​、`<iframe>`。
       2. ​**​`href`​**​  **(Hypertext Reference):**

          1. **用于建立当前文档与外部资源的关系，通常并行下载**
          2. 指向网络资源，定义当前元素与引用资源之间的链接关系。它不嵌入内容，而是建立链接。常见于 `<link>`​、`<a>`
    8. **img 的 alt vs title**

       1. alt：用于存储图片的替代文本；当图片因网络错误、内容屏蔽或链接失效等原因无法加载时，替代文本也会在页面上显示。
       2. title：当光标停留在图像上时会短暂显示。
    9. **空元素**

       1. 概念：空元素是指在HTML中不需要成对出现（即没有结束标签`</tag>`）的元素。它们通常仅由开始标签构成，且根据规范，它们不应包含任何子元素或文本内容。
       2. 常见空元素：

          1. -    
               (换行)
             - ​`<hr>` (水平线)
             - ​`<img>` (图像)
             - ​`<input>` (输入框)
             - ​`<link>` (链接样式表)
             - ​`<meta>` (元信息)
             - ​`<col>` (表格列属性)
    10. **Canvas vs SVG**

        1. Canvas：

           1. 基于像素（Raster/Bitmap），基于 API 绘制，绘制后不被 DOM 记录
           2. Canvas 放大后会出现像素化（失真）。
           3. Canvas 依赖 JavaScript 在像素层面处理鼠标/触摸事件。
           4. Canvas 适合频繁变更图像、像素处理、高交互、大数据量场景（如游戏、绘图板、复杂动画）。
        2. SVG：

           1. 是基于 DOM 的矢量图，绘制的图形是 DOM 元素；
           2. SVG 放大不会失真；
           3. SVG 支持事件处理器（每个元素可绑定事件）
           4. SVG 适合小型图形、图标、动态图表（如地图、SVG 图标）；
    11. 本地存储方式

        1. Cookies：数据量小（4KB），有效期可设置，每次请求自动发送到服务器。

           1. 登录态（Session ID）、用户偏好设置。
        2. localStorage：数据量大（通常5MB+），永久存储，除非主动删除，不与服务器通信。

           1. 永久缓存、购物车数据、皮肤主题。
        3. sessionStorage：数据量大（5MB+），仅在当前标签页/窗口关闭前有效。

           1. 单次表单填写、敏感的一次性数据。
        4. Web SQL：
        5. IndexedDB：用于存储大量结构化数据
    12. **[离线存储 (Manifest/PWA)](https://www.cnblogs.com/bala/p/14529449.html)**

        1. **什么是Service Worker？它如何实现离线功能？**

           1. 原理：运行在浏览器背后的独立线程，拦截网络请求。
           2. 流程：注册 -\> 安装（缓存资源） -\> 激活（处理更新） -\> 拦截请求（返回缓存资源或请求网络）。
    13. Web Workers

        1. 概念：Web Worker 是 HTML5 标准的一部分，允许 JavaScript 脚本在浏览器主线程之外的后台线程中运行，从而避免长时间的计算阻塞 UI 渲染。
        2. 优势：后台线程运行JS，不阻塞主进程；提升 Web 应用程序的性能和响应速度，实现多线程并发操作，让界面在处理繁重任务时保持流畅。
        3. **Web Worker 和主线程的区别？**  答：Web Worker 无法访问 DOM、BOM、`window`​ 对象（但在工作线程中有 `self`），且独立于其他脚本运行
        4. 局限性：不能操作DOM
    14. [WebSocket](https://juejin.cn/post/7288963909591138344)

        1. 概念：WebSocket 作为一种基于 TCP 协议的实时通信协议，为前端应用提供了强大的双向通信能力。
        2. WebSocket 协议和 HTTP 协议的区别是什么？

           1. 连接方式：WebSocket 提供持久的连接，通过握手过程建立连接后保持打开状态，而 HTTP 是无状态的，每次请求都需要重新建立连接。
           2. 数据格式：WebSocket 支持文本和二进制数据的传输，而 HTTP 主要是传输文本数据。
           3. 数据传输方式：WebSocket 实现了全双工通信，客户端和服务器可以同时发送和接收数据，而 HTTP 是单向的，客户端发起请求，服务器响应数据。
           4. 协议标识：WebSocket 使用 ws:// 或 wss:// 前缀标识，而 HTTP 使用 http:// 或 https://
        3. 优势

           1. 实时性：WebSocket 提供了低延迟的实时通信能力，能够在服务器端有新数据时立即推送给客户端。
           2. 双向通信：WebSocket 支持客户端和服务器之间的双向通信，可以实现实时聊天、实时数据更新等场景。
           3. 较低的网络开销：WebSocket 使用长连接，相对于频繁的短连接请求，减少了网络开销。
           4. 更高的性能：由于减少了 HTTP 请求的开销，WebSocket 在性能上更高效。
           5. 跨域支持：WebSocket 具备跨域通信的能力，可以跨域进行实时通信。
        4. 连接过程？
    15. DOM和BOM区别

        1. ​**DOM (Document Object Model)** ：旨在提供操作网页内容的接口，将HTML文档表示为节点树结构。
        2. **BOM (Browser Object Model)** ：旨在处理浏览器窗口、标签页、屏幕信息及导航功能。
        3. **BOM 包含 DOM**。BOM 的顶层对象是 `window`​，而 `window.document` 也是 BOM 的一部分，但它指代的是 DOM 模型。
        4. ​**主要用例**：

           - ​**DOM**：改变元素颜色、添加节点、读取属性。
           - ​**BOM**：弹出警告框、控制页面跳转、获取窗口尺寸

    ‍

    # 进阶

    1. 页面生命周期

       1. ​`DOMContentLoaded`：浏览器已完全加载 HTML，并生成了 DOM 树，但此时不包含外部样式、图像等资源。DOM 操作在此事件中进行。
       2. ​`load`：浏览器不仅加载了 HTML，还加载了所有外部资源（图片、样式、iframe），此时页面已完整呈现。
       3. ​`beforeunload`​：当浏览器窗口关闭或者刷新时，会触发 **​`beforeunload`​** 事件。当前页面不会直接关闭，可以点击确定按钮关闭或刷新，也可以取消关闭或刷新。
       4. 顺序：解析 HTML -> 遇到 async 脚本（异步加载）-> 遇到 defer 脚本（异步加载）-> DOM树生成 (DOMContentLoaded) -> 图片等资源加载完毕-> window.onload。
    2. **XSS和CSRF攻击？** 

       1. **XSS (Cross-Site Scripting) 跨站脚本攻击**

          1. 攻击类型

             1. 反射型（Reflected）：代码在 URL 参数中，需诱导用户点击。
             2. 存储型（Stored）：代码存储在服务器数据库，影响所有访问用户（危害最大）。
             3. DOM 型（DOM-based）：完全由前端 JS 渲染，无需服务器参与。
          2. 危害

             1. 窃取 Cookie（例如 `document.cookie`）、Session，冒充用户登录。
             2. 读取敏感数据、修改 DOM 页面结构、钓鱼欺诈。
          3. 如何预防？

             1. **输入过滤/过滤：**  对用户输入内容进行转义（如 `<`​, `>`​, `"`），使用转义库。
             2. **设置 HttpOnly：**  关键 Cookie 设置 `HttpOnly`，防止 JS 读取。
             3. **内容安全策略 (CSP)：**  限制浏览器只加载受信任的资源，禁用内联脚本
       2. **CSRF (Cross-Site Request Forgery) 跨站请求伪造**

          1. 原理：攻击者诱导用户访问恶意网站，通过用户在被信任网站的登录状态（Cookie），强制浏览器向第三方网站发送非法操作请求（如转账、修改密码）。
          2. 如何预防

             1. **检查 Referer/Origin 头：**  确认请求来源是否合法。
             2. **使用 Token 验证：**  在请求中加入随机 Token，服务器校验其有效性。
             3. **SameSite Cookie 属性：**  设置 Cookie 的 `SameSite`​ 为 `Strict`​ 或 `Lax`，禁止跨站携带 Cookie。
       3. 区别

          1. XSS 主要是​**窃取数据**，核心是“注入恶意代码”。
          2. CSRF 主要是​**冒名操作**，核心是“冒用 Cookie”。
    3. **[无障碍 (ARIA)？](https://developer.mozilla.org/zh-CN/docs/Learn_web_development/Core/Accessibility/HTML#html_%E5%92%8C%E6%97%A0%E9%9A%9C%E7%A2%8D)**

       1. 概念：用正确的 HTML 标签来表达正确的意图
    4. 跨页面通讯方式

       1. **localStorage (最常问):**  利用 `window.addEventListener('storage', ...)` 监听变化，简单且持久，但不适合大数据量。
       2. **BroadcastChannel API:**  专为浏览器上下文间通信设计，实现同源下多标签页广播。
       3. **Shared Worker**: 运行在独立线程，实现跨页面共享数据，适合复杂场景。
       4. **cookie + setInterval:**  轮询查询 cookie 变化，效率较低。
       5. url传参
       6. postMessage
    5. http连接过程？

       1. ​**TCP三次握手**：为何需要三次？（确认双方收发能力）。
       2. ​**TCP四次挥手**：为何需要四次？（确保数据传输完毕）。
    6. **[cookie](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Guides/Cookies)**

       1. 概念：它是服务器发送到用户浏览器并保存在本地的一小块数据，会在后续请求中自动带回服务器。
       2. 常用属性

          1. **HttpOnly：**  防止跨站脚本（XSS）攻击，禁止 JS 读取 Cookie。
          2. **Secure：**  确保 Cookie 仅通过 HTTPS 协议传输。
          3. **SameSite：**  解决 CSRF（跨站请求伪造）问题，可设置为 `Strict`​（严格）、`Lax`​（默认）或 `None`（需伴随 Secure）。
          4. **Cookie 属性限制：**  Chrome 等浏览器已将 Cookie 有效期限制在 400 天以内。
          5. Name（名称）
          6. Value（值）
          7. Domain（域名）
          8. Path（路径）
          9. Expires/Max-Age（有效期）
    7. 预加载（preload）和预请求（prefetch）

       1. 区别：

          1. 预加载（preload）：`preload`​ 旨在告知浏览器**当前**页面马上需要资源（如字体、首屏CSS），提升当前加载优先级；
          2. 预请求（prefetch）：`prefetch`​ 旨在告知浏览器**未来**（下一个页面或用户操作后）可能需要的资源，在空闲时下载到缓存。
       2. 适用场景

          1. ​`preload`用于首屏必需的脚本、样式表、字体文件。
          2. ​`prefetch` 用于二级页面、复杂的交互逻辑代码等。


[^2]: # 知识总结

    # 基础

    1. 块级元素和行内元素？

       1. 块级元素

          1. 概念：独占一行
          2. **宽高设置有效（默认父容器100%）** ，**边距 (Margin/Padding)设置有效，可包含块级和行内**
          3. div、p、h1、ul、form、li
       2. 行内元素

          1. 概念：不独占一行，水平排列，内容撑开宽度
          2. **宽高由内容决定，宽高设置无效，边距 (Margin/Padding)水平方向设置有效，垂直方向无效。**
          3. span、a、strong、em、i
       3. 行内块级元素

          1. 概念：既可在一行内排列（像行内元素），又可以设置宽高和内外边距（像块级元素）。
          2. img、button、input、textarea
    2. 选择器

       1. ​ **​`!important`​**：最高优先级
       2. 内联：1000
       3. id选择器：100
       4. 类、属性、伪类选择器：10
       5. 元素、伪元素选择器：1
       6. 通配符、子选择器：0
    3. 继承属性

       1. 可继承属性

          1. 概念：会继承父元素的属性
          2. **文字控制和视觉表现相关的属性可继承**
          3. color、font、line-height、font-size、`visibility`​、`cursor`
       2. 不可继承属性

          1. 概念：不会继承父元素的属性
          2. **盒模型相关的属性通常不能继承**
          3. margin、padding、width、height、border
       3. **继承属性优先级？**

          1. **继承属性的优先级极低**，子元素可用任何选择器覆盖属性。
       4. **强制继承一个不可继承的属性？**

          1. ​`inherit`
       5. **CSS中的** **​`inherit`​**​ **,**  **​`initial`​**​ **,**  **​`unset`​**​ **有什么区别？**

          1. ​`inherit`：显式继承父元素的属性值。
          2. ​`initial`​：将属性设置为浏览器默认的初始值（如 `color: initial` 可能是黑色）。
          3. ​`unset`​：如果属性是继承的，则表现为 `inherit`​；否则表现为 `initial`
    4. 伪类和伪元素

       1. 伪类：

          1. 概念：选择处于特定状态的元素
          2. 主要功能：交互、结构选择。
          3. ​`:hover`​、`:active`​、`:focus`​、`:first-child`​、`:last-child`​、`:nth-child(n)`
       2. 伪元素：

          1. 概念：选择元素的特定部分
          2. 主要功能：内容生成、格式化部分内容。
          3. ​`::before`​、`::after`​、`::first-letter`​、`::first-line`​、`::selection`
    5. CSS盒模型

       1. 概念：由 <span data-type="text" style="background-color: var(--b3-font-background12);">Content (内容)、Padding (内边距)、Border (边框)、Margin (外边距) </span>组成。
       2. 标准盒模型

          1. Width/Height \= Content。
          2. ​`box-sizing: content-box`
       3. IE盒模型

          1. Width/Height \= Content + Padding + Border。
          2. ​`box-sizing: border-box`
          3. 优势：设置border、padding不会撑大元素尺寸，布局更方便，利于响应式设计。
       4. margin重叠or塌陷

          1. 相邻的块级元素垂直外边距会合并为最大者。
          2. **解决：使用BFC（如****​`overflow: hidden`​**​​ **）、给父级加padding、或设置border**​ **。**
    6. 像素单位区别

       1. 基础

          1. px：绝对单位，像素级精确控制，适合边框、阴影。
          2. em：相对单位，**相对于父元素字体大小**，适合字体和行高。
          3. rem：相对单位，**相对于根元素（**​ **​`<html>`​** ​ **）字体大小**，是移动端适配主流方案。
          4. 百分比：相对单位，相对于父元素的对应属性计算。
          5. vw/vh：视口单位，基于视口宽度/高度的百分比，适合响应式全屏布局。
       2. 响应式布局如何选单位：

          1. 字体大小用 rem 或 px（需要精细控制），容器宽度用 % 或 vw，边框、间距通常用 px。
       3. **rem 适配方案的原理是什么？**

          1. 通过动态修改 `<html>`​ 节点的 `font-size`（通常配合媒体查询或 JS），使所有使用 rem 的元素根据屏幕宽度等比例缩放
       4. 物理像素和css像素

          1. 物理像素：硬件设备显示的最小区域
          2. css像素：是Web开发者使用的抽象单位，在高清屏（Retina）上，一个CSS像素通常对应多个物理像素
          3. DPR：DPR = 物理像素/css像素
       5. 媒体查询（media）

          1. 概念：它允许根据媒体类型（如 `screen`​, `print`）或媒体特性（如视口宽度、屏幕方向）定义不同的 CSS 样式。
          2. **断点（Breakpoints）如何选取：** 常见依据：`480px`​ (手机), `768px`​ (平板), `1024px`​ (笔记本), `1200px` (桌面)。
          3. **为什么需要**  **​`<meta name="viewport" content="width=device-width, initial-scale=1.0">`​** ​ **？**

             1. 这是为了让媒体查询正常工作，强制移动端视口等于设备实际宽度，否则会按照默认宽度（通常为980px）渲染。
    7. ​`display`​、`visibility`​、`opacity` 区别

       1. ​`display`：none

          1. 不占空间，不响应事件
          2. 触发回流(Reflow)和重绘
       2. ​`visibility`：hidden

          1. 子元素继承该属性
          2. 占空间、不响应事件
          3. 仅触发重绘(Repaint)
       3. ​`opacity`：0

          1. 子元素继承该属性
          2. 占空间，响应事件
          3. 仅触发重绘(Repaint)
    8. **BFC (块级格式化上下文)**

       1. 概念：Block Formatting Context（块级格式化上下文），是页面CSS渲染的一个独立区域，内部元素不会影响外部
       2. 如何触发？

          1. ​`overflow`​不为`visible`​（如`hidden`​、`auto`）
          2. ​`float`​不为`none`
          3. ​`position`​为`absolute`​或`fixed`
          4. ​`display`​为`inline-block`​、`table-cell`​、`flex`等
       3. **BFC的布局规则/特性？**

          1. 内部盒子在垂直方向上一个接一个放置。
          2. 内部垂直方向Margin会重叠。
          3. BFC区域不会与浮动元素重叠。
          4. 计算BFC高度时，浮动元素也参与计算（清除浮动）。
          5. 区域独立，互不干扰。
       4. **能解决什么问题？**

          1. **解决容器高度塌陷**
          2. **防止垂直Margin重叠**
          3. **自适应两栏布局**
    9. **Link vs @import**

       1. 核心区别（本质与加载顺序）：

          1. **本质不同**：`link`​ 属于 HTML 标签，不仅能引入 CSS，还能引入icon，字体等；而 `@import` 是 CSS 提供的语法，只能引入 CSS 文件。
          2. ​**加载顺序**​：页面加载时，`link`​ 引用的 CSS 会与 HTML 并行加载；而 `@import` 需要等待页面完全载入后才开始加载。
          3. **加载速度**：由于并行加载，`link`​ 性能更优，能确保页面样式在渲染时已准备好；`@import` 可能导致页面短暂“闪烁”（无样式内容）
       2. 性能与兼容性

          - ​**性能**​：`link`​ 优于 `@import`。
          - **兼容性**：`@import`​ 是 CSS2.1 引入的，老旧浏览器（如 IE5）不兼容，而 `link` 无兼容性问题。
       3. DOM 操作与功能

          - ​**DOM 控制**​：`link`​ 标签可以通过 JS 操作（例如 `document.createElement('link')`）动态引入样式。
          - **功能**：`link` 具有丰富的 rel 属性，可用于引入图标等
    10. CSS3新特性

        1. flex、grid布局
        2. 动画

           1. ​`transform`：平移、旋转、缩放。
           2. ​`transition`：过渡效果。
           3. ​`animation`​：`@keyframes` 动画。
        3. **图形与视觉：**  `border-radius`​（圆角）、`box-shadow`​（阴影）、`gradient`​（渐变）、`opacity`（不透明度）
        4. **新特性：**  `box-sizing`​（盒模型计算）、`calc()`​（计算函数）、媒体查询（`@media`）。

    ‍

    # 进阶

    1. 回流(Reflow)和重绘(Repaint)

       1. 回流(Reflow)：

          1. 概念：当渲染树（Render Tree）中元素的布局信息（位置、尺寸、隐藏/显示）发生改变时，浏览器需要重新计算元素几何属性的过程。
          2. <span data-type="text" style="background-color: var(--b3-font-background12);">回流必定会导致重绘，但重绘不一定会导致回流</span>。
          3. 触发条件：

             1. DOM 元素增删、位置或尺寸改变。
             2. 计算 `offsetWidth`​、`scrollTop` 等属性（会强制重排）。
             3. 浏览器窗口尺寸变化。
             4. 改变字体大小、修改样式表。
       2. 重绘(Repaint)：

          1. 概念：当元素的外观（背景色、颜色、visibility 等）发生改变，但不影响布局时，浏览器重新绘制元素的过程。
          2. 触发条件：

             1. 修改颜色（color, background-color）。
             2. ​`visibility` 改变。
             3. ​`box-shadow` 等外观属性改变
       3. 如何优化

          1. ​**CSS 优化**​：使用 `transform`​ 代替 `top/left`​ 做动画，使用 `visibility`​ 代替 `display:none`。
          2. ​**DOM 操作**​：合并 DOM 操作（使用 `DocumentFragment` 或一次性更新），批量修改样式。
          3. ​**CSS 属性**​：避免在循环中读取 `offsetTop` 等导致强制重排的属性。
    2. **层叠上下文 (Z-index)**

       1. 概念：`z-index`​ **属性设置定位元素（** **​`position`​**​​ **不为** **​`static`​**​​ **）的堆叠顺序**。数值大的元素会覆盖数值小的元素。
       2. 产生条件：

          1. 根元素 `<html>`
          2. ​`position`​ 为 `absolute`​/`relative`​ 且 `z-index`​ 不为 `auto`
          3. ​`position: fixed`​/`sticky`、
          4. ​`flex`​/`grid`​ 的子元素（`z-index`​ 不为 `auto`）、
          5. ​`opacity` 小于 1、
          6. ​`transform`​ 不为 `none`​、`will-change` 等。
       3. **层叠上下文的层叠顺序：** 背景/边框 -\> 负 `z-index`​ -\> 块级元素 -\> 浮动元素 -\> 行内元素 -\> `z-index: 0`​ / `auto`​ -\> 正 `z-index`。
    3. **水平垂直居中**

       1. ​`display: flex; justify-content: center; align-items: center;。`
       2. **绝对定位方法**

          1. 父元素 `relative`​，子元素 `absolute`。

             1. **已知宽高：**  `top: 50%; left: 50%; margin-top: -高/2; margin-left: -宽/2;`。
             2. **未知宽高：**  `top: 50%; left: 50%; transform: translate(-50%, -50%);`
       3. **网格布局（Grid）：** 父元素 `display: grid;`​，子元素 `place-items: center;`
       4. **文本或行内元素水平垂直居中**

          1. 设置 `height`​ 和 `line-height` 相等
       5. **块级元素水平居中**

          1. 定宽块级元素：设置 `margin: 0 auto;`
    4. Flex/Grid布局

       1. flex:

          1. 概念：弹性布局（`Flexible Box`），

             1. 采用Flex布局的元素，称为`flex`​容器`container`​；它的所有子元素自动成为容器成员，称为`flex`​项目`item`
             2. 容器中默认存在两条轴，主轴和交叉轴，呈90度关系。项目默认沿主轴排列，通过`flex-direction`来决定主轴的方向
          2. ​**​`flex: 1`​**​ **到底代表什么？**

             1. 概念：`flex-grow: 1`​, `flex-shrink: 1`​, `flex-basis: 0%` 的缩写
             2. ​`flex-grow`​：项目的放大比例（容器宽度\>元素总宽度时如何伸展），默认为`0`，即如果存在剩余空间，也不放大
             3. ​`flex-shrink`​：定义了项目的缩小比例（容器宽度\<元素总宽度时如何收缩），默认为1，即如果空间不足，该项目将缩小
             4. ​`flex-basis`​：设置的是元素在主轴上的初始尺寸，所谓的初始尺寸就是元素在`flex-grow`​和`flex-shrink`生效前的尺寸；当设置为0的是，会根据内容撑开。
          3. justify-content：定义了项目在主轴上的对齐方式

             1. space-between：两端对齐，项目之间的间隔都相等：|[]      []|
             2. space-around：项目两侧间隔相等（两个项目之前是两倍距离）：| []  []  [] |
             3. space-evenly：所有项目之间的间隔相等：| [] [] [] [] |
          4. align-items：定义项目在交叉轴上如何对齐
       2. grid

          1. 概念：`Grid` 布局即网格布局，是一个二维的布局方式，由纵横相交的两组网格线形成的框架性布局结构，能够同时处理行与列
          2. 优势：Grid更擅长处理复杂的页面结构
          3. [CSS Grid 网格布局教程](https://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html)
          4. ​`grid-template-columns`​属性定义每一列的列宽，`grid-template-rows`属性定义每一行的行高。
          5. ​`grid-row-gap`​属性设置行与行的间隔（行间距），`grid-column-gap`属性设置列与列的间隔（列间距）。
       3. 区别：flex是一维布局，grid是二维布局
    5. **浮动与清除**

       1. 概念：解决父元素高度塌陷。（浮动元素脱离文档流，不占据空间，导致父元素高度无法自动撑开，影响后续元素布局）
       2. 方式：

          1. **[伪元素方法](https://cloud.tencent.com/developer/article/2190051)**​ **（推荐，最常用）：**  给父级添加 `::after`​ 伪元素，设置 `content: ""; display: block; clear: both; height: 0; visibility: hidden;`。
          2. **BFC 方法：**  父元素触发 BFC（如 `overflow: hidden;`​ 或 `display: flow-root;`），利用 BFC 计算高度时包含浮动元素的特性。
          3. **clear 属性：**  在浮动元素下方添加空元素并设置 `clear: both`。
          4. **父级浮动：**  父级也设置浮动，不推荐，会产生新问题。
    6. **定位 (Position)**

       1. 值和作用

          1. ​**static**: 默认值，正常文档流。
          2. ​**relative**​: 相对定位，相对于自身在文档流中的原始位置定位，​**不脱离文档流**。
          3. ​**absolute**​: 绝对定位，相对于最近的非 static 祖先元素定位，​**脱离文档流**。
          4. ​**fixed**​: 固定定位，相对于浏览器视窗（viewport）定位，​**脱离文档流**，滚动不随之移动。
          5. **sticky**: 粘性定位，基于用户滚动位置在 `relative`​ 和 `fixed` 之间切换。
       2. absolute和fixed区别

          1. ​`fixed`​ 是相对于浏览器窗口，`absolute` 是相对于定位父级。
       3. sticky失效条件

          1. ​**必须设置阈值**​：必须至少指定 `top`​、`right`​、`bottom`​ 或 `left`​ 中的一个（例如 `top: 0`）。
          2. ​**父元素限制**：

             - 父元素不能设置 `overflow:hidden`​ 或 `overflow:auto`。
             - 必须确保父元素有足够的高度，否则 `sticky` 元素没有滚动空间
       4. ​**​`relative`​**​ **对自身和父元素有什么影响？**

          1. 不脱离文档流，可以通过 `top/left`​ 移动，常用于作为 `absolute` 元素的父级。
    7. **CSS 动画**

       1. **[Transition（过渡）](https://www.google.com/search?q=Transition%EF%BC%88%E8%BF%87%E6%B8%A1%EF%BC%89&sca_esv=0555e3765a0d8a6a&sxsrf=ANbL-n4BoZ-Wg7vhFsh7reQ_i6gDF1Nwbw%3A1772679675317&ei=-_GoaYWJE5jU1e8PzMTA8Aw&biw=1601&bih=898&ved=2ahUKEwiV-4fU4oeTAxVhevUHHQubDXYQgK4QegQIAxAB&uact=5&oq=css+%E5%8A%A8%E7%94%BB%E9%9D%A2%E8%AF%95%E9%A2%98%E9%97%AE%E4%BB%80%E4%B9%88&gs_lp=Egxnd3Mtd2l6LXNlcnAiHGNzcyDliqjnlLvpnaLor5Xpopjpl67ku4DkuYgyBRAhGKABSM0rULQGWKkqcAN4AZABAZgBzwOgAccaqgEKMy4xNi4yLjAuMbgBA8gBAPgBAZgCGKAC3xfCAgoQABiwAxjWBBhHwgINEAAYgAQYsQMYQxiKBcICCxAAGIAEGLEDGIMBwgIREC4YgAQYsQMY0QMYgwEYxwHCAg4QABiABBixAxiDARiKBcICDRAAGIAEGLEDGIMBGAzCAgoQABiABBixAxgMwgIFEAAYgATCAg0QLhiABBixAxiDARgMwgIGEAAYAxgMwgIHEAAYgAQYDMICBxAuGIAEGAzCAgoQABiABBhDGIoFwgIEEAAYA8ICBRAAGO8FmAMAiAYBkAYKkgcGNS4xNy4yoAe3PrIHBjIuMTcuMrgH1BfCBwYwLjE1LjnIBz-ACAA&sclient=gws-wiz-serp&mstk=AUtExfBjxkfXXtIc-1evwbIaTH_fOp1Jjau6Nrom-FtE-GMYB5XKseYwJGvGcN2m7VP5oOtRKWnST2YpjcVCyEpc9RQ9XEZFTzNgt6jJmk5HMRxdHOyHKRoXbMhiOEaPQ3Dix7FvfGcyKcuAccxNjt2X4MHMHaImnWFKP3dXmCsvwYWqZTvMy-Mfje_HP4PMlca5WZtLAeKeUObJmG-J8e0RxUoxNH8iF9cw3i5R3Ypj1gTfNUPHfPZFZP1y5-kcfNyd0skIxBkp4C3XQmSXrAfLtQ6gtEXSLOKVmTB_iUjbbHaJJDY9SK2LMFMbXIEa9o28IGUQ0PpAc_5ABD2R3xPJ23nL4hnzVQadUl6KUQNSJrKhk9aoobVeBG78dPEz_Zl-cC3zh4n3UcJtf6onba-nTQ&csui=3)**​**与Animation（动画）的区别**

          1. Transition：需要触发（如`:hover`），仅开始和结束两个状态。
          2. Animation：可设置关键帧（`@keyframes`），能定义多个状态，无需触发可自动播放，可暂停、循环。
       2. **动画属性详解**

          - ​`animation-duration`：持续时间。
          - ​`animation-timing-function`：速度曲线（linear, ease-in, cubic-bezier）。
          - ​`animation-delay`：延迟时间。
          - ​`animation-iteration-count`：播放次数（infinite）。
          - ​`animation-direction`：方向（normal, reverse, alternate）。
          - ​`animation-fill-mode`：填充模式（forwards, backwards, both）。
       3. **关键帧**

          1. 使用`@keyframes name { 0% { } 50% { } 100% { } }`
          2. 控制元素从一种样式逐步改变为另一种样式
       4. **如何开启硬件加速？** ：使用 `will-change: transform;`​ 或者 `transform: translateZ(0);`
       5. ​**哪些CSS属性适合做动画？** ​：优先使用 `transform`​ (translate, rotate, scale) 和 `opacity`，因为它们不会触发浏览器的重排（Reflow）和重绘（Repaint），仅触发复合（Composite）。
    8. **Transform**

       1. **常用函数：**  `translate()`​ (平移), `rotate()`​ (旋转), `scale()`​ (缩放), `skew()`​ (倾斜), `matrix()` (矩阵，高级)。
       2. **3D转换：**  `translate3d`​, `rotate3d`​, `perspective`​（透视），以及 `backface-visibility`（隐藏背面）
       3. **GPU加速：**  `transform`​ 不会触发布局（Layout）或重绘（Paint），仅触发复合（Composite），因此性能好。使用 `translate3d(0,0,0)`​ 或 `translateZ(0)` 可以强制开启硬件加速。
       4. 优势：

          1. **避开重排与重绘：** <span data-type="text" style="background-color: var(--b3-font-background1);"> 使用 </span>`transform`​​<span data-type="text" style="background-color: var(--b3-font-background1);"> 移动元素（如 </span>`translate`​​<span data-type="text" style="background-color: var(--b3-font-background1);">）时，不会触发页面文档流的重新计算（重排）和像素绘制（重绘）。</span>
          2. **合成层机制：** <span data-type="text" style="background-color: var(--b3-font-background1);"> 变换过程通常在 GPU 上完成，利用显卡加速，使得动画极其平滑。</span>
    9. **[浏览器解析流程](https://zhuanlan.zhihu.com/p/561696825)**

       1. ![dom树](./images)
       2. **解析过程**

          1. ​**[DOM树](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=DOM%E6%A0%91&zhida_source=entity)**​**构建**​：[渲染引擎](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=%E6%B8%B2%E6%9F%93%E5%BC%95%E6%93%8E&zhida_source=entity)使用HTML解析器（调用XML解析器）解析HTML文档，将各个HTML元素逐个转化成DOM节点，从而生成DOM树；
          2. ​**[CSSOM树](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=CSSOM%E6%A0%91&zhida_source=entity)**​**构建**：CSS解析器解析CSS，并将其转化为CSS对象，将这些CSS对象组装起来，构建CSSOM树；
          3. ​**[渲染树](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=%E6%B8%B2%E6%9F%93%E6%A0%91&zhida_source=entity)**​**构建**：DOM 树和 CSSOM 树都构建完成以后，浏览器会根据这两棵树构建出一棵渲染树；
          4. ​**[页面布局](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=%E9%A1%B5%E9%9D%A2%E5%B8%83%E5%B1%80&zhida_source=entity)**：渲染树构建完毕之后，元素的位置关系以及需要应用的样式就确定了，这时浏览器会计算出所有元素的大小和绝对位置；
          5. **[页面绘制](https://zhida.zhihu.com/search?content_id=212954202&content_type=Article&match_order=1&q=%E9%A1%B5%E9%9D%A2%E7%BB%98%E5%88%B6&zhida_source=entity)**：页面布局完成之后，浏览器会将根据处理出来的结果，把每一个页面图层转换为像素，并对所有的媒体文件进行解码。
       3. **DOM树和CSSOM树并行解析**

          1. **并行解析：**  DOM解析器一边解析HTML生成节点，CSS解析器一边根据样式表生成CSSOM。
          2. **阻塞规则：**  尽管并行，但CSS是“渲染阻塞资源”。在CSSOM完全构建完成前，浏览器不会渲染页面。
          3. **JS干扰：**  如果解析过程中遇到非异步JS，DOM解析会暂停，此时如果CSS文件未加载完成，JS必须等待CSSOM加载完成后才能执行，避免JS操作未定义样式。
    10. 预处理器

        1. 概念：它是一种扩充了CSS语言的工具，增加了变量、函数、逻辑控制等特性，解决了原生CSS难以复用、维护困难、嵌套繁琐等问题。
        2. **与后处理器（postcss）区别**：<span data-type="text" style="background-color: var(--b3-font-background1);">预处理器（Sass/Less）在编译前运行，增加特性；后处理器（PostCSS）在编译后对CSS进行优化（如自动补全前缀），如Autoprefixer。</span>
        3. **常用特性有哪些？**

           1. ​**嵌套 (Nesting)** ：减少选择器重复编写。
           2. ​**变量 (Variables)** ：统一管理颜色、字号等，方便换肤。
           3. ​**混入 (Mixin)** ：复用代码块，支持参数，常用于清除浮动、Flex布局。
           4. ​**继承 (Extend/Extend %selector)** ：共享特定规则，减少代码量。
           5. **函数 (Functions) 与逻辑控制**：`@if`​, `@for`​, `lighten()`​, `darken()`。
        4. **Sass/Less/Stylus的区别？**

           1. ​**Sass (SCSS)** ：功能强大，生态成熟，配合Compass更佳。
           2. ​**Less**：上手简单，兼容CSS，常用于Ant Design等项目。
           3. ​**Stylus**：语法最灵活，支持省略分号、花括号。
    11. **后处理器（postcss）**

        1. 概念：是在CSS生成后，对生成的CSS进行处理和优化
        2. **为什么需要使用PostCSS？：** 提升开发效率，自动化处理兼容性，通过插件实现模块化
        3. **PostCSS的原理是什么？**  (解答：它将CSS解析成抽象语法树（AST），插件在AST上进行修改，最后将AST转换回CSS字符串)。
        4. 项目实际运用？：

           1. **如何使用PostCSS实现px到rem的转换？**  (考察对postcss-pxtorem插件的理解)。
           2. **CSS后处理器如何处理CSS兼容性问题？**  (考察使用`postcss-preset-env`将现代CSS转为低版本浏览器兼容的CSS)。
           3. **如何利用后处理器压缩CSS代码？**  (考察对`cssnano`插件的运用)。

    ‍


[^3]: # 知识总结

    详情请查看js基础知识[^4]

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
    8. 变量提升和函数提升

       1. 变量提升

          1. var：声明会被提升到作用域顶部，但**赋值不会**。在声明前访问会得到 `undefined`。
          2. const、let：`let`​ 和 `const`​ 声明也会被提升，但在初始化之前不允许访问。面试官常问：“`let`​ 到底有没有提升？”（**答案是有提升，但没有初始化，处于死区**）。【**暂时性死区：** <span data-type="text" style="background-color: var(--b3-font-background12);">因未初始化而不可被访问的阶段，</span>抛出 `ReferenceError` 错误】
       2. 函数提升

          1. ​**函数声明（Function Declaration）** ​：会被​**完整提升**。你可以在声明行之前调用该函数。
          2. **函数表达式（Function Expression）** ：如果是用 `var`​ 定义的，仅变量名提升，值为 `undefined`​，此时调用会报错 `TypeError: ... is not a function`。
       3. 同名的变量和函数同时提升时优先级？

          1. **函数优先**：函数声明的提升权重高于变量声明（var）。
          2. **后续赋值覆盖**：提升只是确定了“坑位”，代码执行阶段的**赋值操作**会覆盖之前的声明。
    9. let、const、var区别

       1. ​**区别**：var为函数级作用域，可重复声明/提升；let/const为块级作用域，不可重复声明。
       2. ​**提升**：var提升并初始化为undefined，let/const提升但不初始化（死区）。
       3. **const特性**：必须初始化，不能重新赋值（对象属性可修改）。
    10. 执行上下文：<span data-type="text" style="background-color: var(--b3-font-background7);">执行上下文是 JavaScript 代码被解析和执行时所在环境的抽象概念</span>

        1. 全局执行上下文和函数执行上下文
        2. 生命周期

           - ​**创建阶段 (Creation Phase)** ：

             - ​**生成变量对象 (VO/AO)** ​：扫描 `var`​ 变量（设为 `undefined`​）和函数声明（全量提升）——这就是**变量提升**的本质。
             - ​**建立作用域链 (Scope Chain)** ：确定当前环境可以访问哪些外部变量。
             - ​**确定** **​`this`​**​ **指向**​：绑定当前执行环境的 `this`。
           - ​**执行阶段 (Execution Phase)** ：

             - 逐行执行代码，完成变量赋值和函数执行
    11. 作用域和作用域链（考察变量可访问性、查找规则及闭包）

        1. 作用域：JS中变量和函数的有效访问范围（全局、函数、ES6块级）。
        2. 作用域链：在当前作用域查找变量，找不到就沿父作用域向上查找，直到全局，这个逐级查找的过程就是作用域链。
    12. 闭包

        1. 闭包是指有权访问另一个函数作用域中变量的**函数**。
        2. 使用场景：数据私有化、柯里化、高级函数（防抖、节流、回调）、模块化
        3. 防止内存泄露：在闭包不再使用时，手动将其引用设为 `null`，触发垃圾回收。
    13. 事件模型（**传播机制、代理模式、兼容性及性能优化**）

        1. 事件流【`addEventListener`​​​​​​​​​<span data-type="text" style="background-color: var(--b3-font-background12);"> 的第三个参数。</span>`false`​​​​​​​​​<span data-type="text" style="background-color: var(--b3-font-background12);">（默认）表示在冒泡阶段触发</span>】

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
    14. 事件循环

        1. 概念：是 JavaScript 处理异步任务的机制
        2. 宏任务：setTimeout、setInterval、I/O、UI渲染
        3. 微任务：promise、async/await、`process.nextTick`
        4. 执行流程是【同步代码 -\> 微任务队列 -\> 宏任务队列 -\> 重新渲染】

           1. 执行同步代码
           2. 执行每一个宏任务之前优先清空微任务队列
        5. dom事件是宏任务：同步代码 -\> 微任务清空 -\> **DOM事件回调(宏任务)**  -\> 微任务清空 -\> 下一个宏任务。
    15. this指向

        1. 函数独立调用默认是window
        2. 方法调用指向最后调用的对象
        3. 用 `new`​ 调用构造函数，`this`​ 指向**新创建的实例对象**。
        4. call、apply、bind指向绑定的对象
    16. 箭头函数和普通函数

        1. this指向不同：箭头函数this由外部作用域确定；普通函数是谁调用指向谁。
        2. 箭头函数没有this不能作为构造函数，普通函数可以
        3. 普通函数有`arguments`，箭头函数用es6剩余参数
        4. 箭头函数**不能用作生成器，** 不能用`yield`
    17. 函数式编程理解

        1. 概念：函数式编程是一种编程范式，强调用纯函数、不可变数据和函数组合来构建程序，避免副作用。
        2. 高阶函数：接收函数作为参数或返回函数的函数。
        3. 纯函数：1. 相同输入 → 相同输出； 2. 不依赖外部状态； 3. 不修改外部变量。
    18. 异步编程

        1. 概念：异步编程是指不会阻塞主线程执行的编程方式。
        2. 实现方式：1. 回调函数（callback）； 2. Promise； 3. Generator；4. async/await
    19. js中继承【JS 的继承本质是基于原型链】

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
    20. class 和 function 有什么区别？【class是构造函数的语法糖】

        1. 变量提升：funciton会提升，class不会
        2. 调用方式：class必须用new，function可作为函数使用，也可作为构造函数调用
        3. 继承机制：`class`​ 通过 `extends`​ 和 `super()`​ 实现了更直观的继承；而构造函数需要手动操作 `prototype`​ 和 `call/apply`。
        4. 静态方法：`class`​ 可以使用 `static`​ 关键字直接定义静态属性和方法；构造函数需要手动挂载到函数对象上（如 `Fn.staticMethod = ...`）
    21. es6新特性

        1. let、const、symbol、map、set、proxy
        2. 箭头函数
        3. 解构赋值、扩展运算符、默认参数
        4. 模版字符串
        5. promise、class、async/await
        6. 模块化（import、export）
    22. script（async、defer）

        1. defer：延迟执行，不阻塞页面，DOM 解析完毕，但在 `DOMContentLoaded` 事件之前执行，defer之间保持顺序执行。
        2. async：异步执行，不阻塞页面，加载完就执行，不保证顺序。
    23. promise.any、promise.all、promise.race、promise.allSellted

        1. any：只要有一个resolve就成功，全部reject就失败
        2. all：全部都成功才fuifulled，只要有一个reject就失败
        3. race：第一个成功/失败的结果
        4. allSellted：不论成功/失败，最后返回全部的结果
    24. Array.some、Array.every

        1. some：只要满足一个
        2. every：全部满足
    25. for...in 和 for... of区别

        1. for...in：遍历对象和数组，
        2. for... of：遍历对象，
    26. set、map、weakSet、weakMap

        1. set：集合，存唯一值。
        2. map：字典，键值对。
        3. weakSet：只能存放对象
        4. weakMap：只能存放对象
    27. 数组和伪数组：

        1. **伪数组：**

           1. **含有length的普通对象，不能使用数组的方法。**
           2. **常见：**​`` document.querySelectorAll('div')` ``​、`arguments`
           3. 转数组：

              1. ​`Array.from(fakeArray)` (ES6推荐)
              2. ​`Array.prototype.slice.call(fakeArray)` (ES5常用)
              3. 扩展运算符: `[...fakeArray]`
    28. js如何判空

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
          6. ​**闭包的错误使用**：函数内创建了大型对象，即使后续不需要，该闭包仍保持引用


[^4]: # js基础知识

    ![js基础](./images)

    # 基础

    ‍

    ## 数据结构有哪些

    > <span data-type="text" style="background-color: var(--b3-font-background7);">原始类型存储在栈中，引用类型存储在堆中（变量名存在栈中、保存指向堆中地址的指针）</span>
    >

    JavaScript共有**7 种基本数据类型（Primitive Types）** 和 **引用数据类型（Reference Types）** 。

    	1. 分别是原始类型： `Undefined`​、`Null`​、`Boolean`​、`Number`​、`String`​、`Symbol`​、`BigInt`。

    	2. 引用类型： `Object`​，`Array`​，`Function`​，`Date`​，`RegExp`​，`Map`​，`Set`。

    undefined vs null

    1. undefined：定义未赋值
    2. null：无值

    ---

    ### 一、基本数据类型（7种）

    这些类型的值是**不可变的**、**直接存储在栈内存中**，包括：

    |类型|示例|说明|
    | ------| ------------| ------------------------------|
    |​`Number`|​`123`​,`3.14`​,`NaN`|包括整数、浮点数、`Infinity`​、`NaN`|
    |​`String`|​`'hello'`​,`"world"`|字符串（文本）|
    |​`Boolean`|​`true`​,`false`|布尔值|
    |​`undefined`|​`let x;`|未赋值的变量默认值|
    |​`null`|​`let x = null`|表示“空”或“无值”|
    |​`Symbol`|​`Symbol('id')`|表示唯一值，常用于对象属性名|
    |​`BigInt`|​`123n`​,`BigInt(10)`|表示超大整数|

    ### 二、引用数据类型（对象类型）

    这些类型的值是**可变的**，实际数据存储在**堆内存中**，变量存储的是引用地址：

    |类型|示例|说明|
    | --------------| --------------| ------------------------------|
    |​`Object`|​`{ name: 'Tom' }`|常规对象|
    |​`Array`|​`[1, 2, 3]`|数组对象|
    |​`Function`|​`function() {}`|函数本质也是对象|
    |​`Date`|​`new Date()`|日期对象|
    |​`RegExp`|​`/abc/`|正则表达式|
    |​`Map`|​`new Map()`|键值对结构，键可以是任意类型|
    |​`Set`|​`new Set()`|无重复值集合|
    |其他内建对象|​`WeakMap`​,`WeakSet`​,`Error`等|特殊用途对象|

    ### 三、基本类型 vs 引用类型的区别

    |比较项|基本类型|引用类型|
    | ----------| ----------------------------------| --------------------------------------|
    |存储位置|栈内存|栈中存引用，真实数据在堆中|
    |是否可变|不可变（例如字符串不能原地修改）|可变（对象、数组等可以修改其内容）|
    |赋值行为|复制的是值本身|复制的是引用地址|
    |比较方式|使用值比较（`===`）|比较的是引用地址（除非手动比较内容）|

    #### 示例比较

    ```js
    // 基本类型：值拷贝
    let a = 1;
    let b = a;
    b = 2;
    console.log(a); // 1

    // 引用类型：引用拷贝
    let obj1 = { name: 'Tom' };
    let obj2 = obj1;
    obj2.name = 'Jerry';
    console.log(obj1.name); // Jerry
    ```
    ‍

    ### 四、类型判断方式

    ​`typeof null 是 'object'`

    |判断方法|适用类型|示例|
    | ----------| -----------------------| ------|
    |​`typeof`|基本类型（除了 null）|​`typeof 123 // 'number'`|
    |​`instanceof`|引用类型|​`[] instanceof Array // true`|
    |​`Object.prototype.toString`|所有类型（更精确）|​`Object.prototype.toString.call(null) // '[object Null]'`|

    ‍

    ## script、defer、async

    |属性|加载|执行时间|顺序|阻塞 HTML？|推荐使用场景|
    | --------| ------| ----------------| ------| -------------| ---------------------------|
    |无属性|同步|加载完立即执行|✅|⛔ 是|内联或必须立即执行的脚本|
    |​`defer`|异步|DOM 完成后执行|✅|✅ 否|页面主逻辑脚本 ✅ 推荐|
    |​`async`|异步|下载完立即执行|❌|✅ 否|独立脚本，如广告/统计代码|

    ‍

    ## cookie、sessionStorage、localStorage、indexDB

    |特性/存储方式|​`cookie`|​`localStorage`|​`sessionStorage`|​`IndexedDB`|
    | ----------------| -------------------------| ------------------------| ---------------------------------| --------------------------|
    |主要用途|与服务器通信、少量数据|本地持久缓存|会话级缓存（临时数据）|存结构化数据（如数据库）|
    |数据容量|\~4KB|约 5\~10MB|约 5\~10MB|上百 MB（浏览器限制）|
    |生命周期|可设置过期时间|除非手动清除，永久保存|页面关闭或标签页关闭即失效|持久存储|
    |是否随请求发送|✅ 是，自动随 HTTP 请求|❌ 否|❌ 否|❌ 否|
    |跨标签页共享|✅ 是|✅ 是|❌ 否（同源但不同窗口不能共享）|✅ 是|
    |支持的数据类型|字符串（需手动编码）|仅支持字符串|仅支持字符串|任意结构化对象|
    |编程接口|简单 (`document.cookie`)|简单 (`localStorage`)|简单 (`sessionStorage`)|较复杂（异步、事务）|
    |安全性|明文传输（需加 HTTPS）|本地访问较安全|本地访问较安全|本地访问较安全|

    ‍

    ### 适用场景

    ‍

    #### 🍪 1. Cookie

    - 原始用途是**浏览器和服务器通信时存储用户状态信息**（如登录状态）。
    - 会随每个请求自动发送到服务器（影响性能）。
    - 可设置过期时间，否则为会话级别。
    - 需手动编码字符串（如 `JSON.stringify()`）。

    ✅ 用于：

    - 服务器端需要读取的数据（如登录凭证）
    - 小体积配置项（如语言偏好）

    ---

    #### 📦 2. localStorage

    - 持久存储本地数据，无过期时间。
    - 存储内容以字符串为主（需手动序列化对象）。
    - 不会随请求发送，提高性能。
    - 同源策略：不同域名之间不能共享。

    ✅ 用于：

    - 登录信息、购物车缓存、本地用户偏好
    - 长时间保留的数据

    ---

    #### 🔄 3. sessionStorage

    - 数据只在**当前标签页或窗口存在时有效**。
    - 页面关闭/刷新后失效，不会共享到新标签页。
    - 同样只能存字符串。

    ✅ 用于：

    - 多步表单填写缓存
    - 临时页面状态管理
    - 防止多个标签页数据冲突（如支付页）

    ---

    #### 🗃️ 4. IndexedDB

    - 面向对象的本地数据库，支持**结构化数据存储**。
    - 异步操作，支持事务、索引查询。
    - 可存储大量数据，且性能好。
    - API 较复杂（推荐用封装库如 `idb`​、`Dexie.js`）。

    ✅ 用于：

    - 离线 Web 应用（如笔记、邮件）
    - 图片、音频等二进制数据缓存
    - 数据量较大的缓存场景（如搜索历史）

    ‍

    ### 总结

    |场景|用什么？|
    | ----------------| -------------------------|
    |与服务器通信|Cookie|
    |跨页面永久存|localStorage|
    |当前标签页用|sessionStorage|
    |存结构化大数据|IndexedDB（本地数据库）|

    ‍

    ‍

    # 进阶

    ‍

    ## 宏任务和微任务

    JavaScript 中的 **宏任务（Macro Task）**  和 **微任务（Micro Task）**  是事件循环（Event Loop）机制的核心组成部分，它们决定了 **代码执行的先后顺序**。理解它们对于掌握异步编程（如 Promise、async/await、setTimeout）至关重要。

    ---

    ### 🧠 一、事件循环模型（Event Loop）基础理解

    浏览器中 JavaScript 的执行机制是 **单线程** 的，它采用“事件循环”来调度任务。

    ### JS 任务类型：

    1. **同步任务**：立即执行（直接写在代码里的逻辑）
    2. **异步任务**：分为两类

       - **宏任务（Macro Task）**
       - **微任务（Micro Task）**

    ---

    ### 🧩 二、宏任务（Macro Task）

    **定义**：宏任务是整体执行的“大任务”，它包括定时器、网络请求回调、UI 渲染等。

    ### 常见宏任务来源：

    |宏任务来源|说明|
    | ------------| -------------------------------------------------------------------|
    |​`setTimeout()`|定时器|
    |​`setInterval()`|重复定时器|
    |​`setImmediate()`|Node.js 中的宏任务|
    |​`MessageChannel`|浏览器的宏任务|
    |​`UI渲染`|浏览器刷新重绘|
    |​`请求完成回调`|如`fetch().then()`​的`.then()`实际属于微任务，但 fetch 完成后进入事件循环是个宏任务阶段|

    ---

    ### 🧵 三、微任务（Micro Task）

    **定义**：微任务是当前宏任务执行完毕后、下一个宏任务开始前立即执行的小任务。

    ### 常见微任务来源：

    |微任务来源|说明|
    | ------------| ----------------------------|
    |​`Promise.then/catch/finally`|最常见的微任务|
    |​`queueMicrotask()`|显式创建微任务|
    |​`MutationObserver`|DOM 变更监听（浏览器 API）|

    ---

    ### 🔄 四、执行顺序规则：宏任务 vs 微任务

    ### **事件循环过程如下**：

    1. 执行一个宏任务（例如 `setTimeout` 回调）
    2. 执行过程中如果遇到微任务（例如 `Promise.then`），先加入微任务队列
    3. 当前宏任务执行结束后，**立即清空微任务队列**
    4. 然后再去执行下一个宏任务
    5. 如此循环...

    ---

    ### 🔍 五、经典例子解析

    #### 示例 1：

    ```js
    console.log('start');

    setTimeout(() => {
      console.log('timeout');
    }, 0);

    Promise.resolve().then(() => {
      console.log('promise');
    });

    console.log('end');
    ```
    ##### 输出顺序：

    ```
    start
    end
    promise
    timeout
    ```
    ##### 执行分析：

    1. ​`start` → 同步
    2. ​`setTimeout` → 宏任务，加入宏任务队列
    3. ​`Promise.then` → 微任务，加入微任务队列
    4. ​`end` → 同步
    5. 当前执行栈清空，开始执行微任务 → `promise`
    6. 微任务清空后 → 执行下一个宏任务 → `timeout`

    ---

    #### 示例 2：多层嵌套微任务和宏任务

    ```js
    setTimeout(() => {
      console.log('macro1');
      Promise.resolve().then(() => {
        console.log('micro1');
      });
    }, 0);

    setTimeout(() => {
      console.log('macro2');
    }, 0);
    ```
    ##### 输出顺序：

    ```
    macro1
    micro1
    macro2
    ```
    > 每个宏任务中的微任务，在对应宏任务执行完后立即清空，**不会跨宏任务“提前执行”** 。
    >

    ---

    ### 🧬 六、Node.js 中的差异（了解）

    Node 中的微任务还包括 `process.nextTick`​，它的优先级高于 `Promise.then`。

    Node 中的宏任务队列分为多个阶段，比如：

    - timers（定时器）
    - pending callbacks
    - idle, prepare
    - poll
    - check（setImmediate）
    - close callbacks

    ---

    ### 🧠 七、总结对比表

    |特性|宏任务（Macro Task）|微任务（Micro Task）|
    | ----------| ---------------------------| ------------------------------|
    |代表 API|​`setTimeout`​,`setInterval`|​`Promise.then`​,`queueMicrotask`|
    |触发时机|每次事件循环的开始|当前宏任务执行结束后立即执行|
    |优先级|低（后执行）|高（先执行）|
    |作用场景|异步控制、定时器、IO 回调|链式异步任务、细粒度异步操作|

    ## 继承

    当然可以！下面是对 **JavaScript 中几种常见继承方式的简单讲解**，不啰嗦、不复杂，直击重点 👇

    ---

    ### ✅ 1. 原型继承

    通过将一个对象作为另一个对象的原型来实现继承。

    ```js
    let parent = {
      sayHi() {
        console.log("Hi from parent");
      }
    };

    let child = Object.create(parent);
    child.sayHi(); // Hi from parent
    ```
    > ✅ 简单：继承了父对象的所有属性/方法  
    > ❌ 缺点：不能传参，属性共享可能有副作用
    >

    ---

    ### ✅ 2. 构造函数继承（伪经典继承）

    在子构造函数中调用父构造函数。

    ```js
    function Parent(name) {
      this.name = name;
    }

    function Child(name) {
      Parent.call(this, name); // 继承属性
    }

    let c = new Child("Liu Yu");
    console.log(c.name); // Liu Yu
    ```
    > ✅ 优点：可以传参，属性不共享  
    > ❌ 缺点：**不能继承方法（prototype）**
    >

    ---

    ### ✅ 3. 组合继承（经典继承）

    构造函数继承 + 原型继承的组合方式。

    ```js
    function Parent(name) {
      this.name = name;
    }
    Parent.prototype.sayHi = function () {
      console.log("Hi, " + this.name);
    };

    function Child(name) {
      Parent.call(this, name); // 继承属性
    }
    Child.prototype = Object.create(Parent.prototype); // 继承方法
    Child.prototype.constructor = Child;

    let c = new Child("Liu Yu");
    c.sayHi(); // Hi, Liu Yu
    ```
    > ✅ 推荐：属性方法都能继承  
    > ❌ 小缺点：调用了两次父构造函数
    >

    ---

    ### ✅ 4. ES6 class 继承（最简洁）

    ```js
    class Parent {
      constructor(name) {
        this.name = name;
      }
      sayHi() {
        console.log("Hi, " + this.name);
      }
    }

    class Child extends Parent {
      constructor(name) {
        super(name); // 必须调用 super
      }
    }

    let c = new Child("Liu Yu");
    c.sayHi(); // Hi, Liu Yu
    ```
    > ✅ 最清晰现代的写法，语法糖背后还是原型链
    >

    ---

    ### 🧠 总结对比

    |方式|是否继承属性|是否继承方法|是否能传参|推荐指数|
    | --------------| --------------| --------------| ------------| ------------|
    |原型继承|✅|✅|❌|⭐⭐|
    |构造函数继承|✅|❌|✅|⭐⭐|
    |组合继承|✅|✅|✅|⭐⭐⭐⭐|
    |​`class`继承|✅|✅|✅|⭐⭐⭐⭐⭐|

    ‍

    ‍

    ## 浏览器从输入url到回车发生了什么

    这是前端开发常见的高频面试题之一，考察的是你对 **网络、浏览器工作原理、前端性能、安全、渲染机制等多个知识点** 的理解。

    下面是一种结构清晰、层次分明、能打动面试官的标准回答方式，建议分 7 个阶段来讲：

    ---

    ### ✅ 1. 地址解析阶段（URL 到 IP）

    - **DNS 解析**：将域名（如 `www.example.com`）解析为服务器的 IP 地址。

      - 浏览器缓存 → 操作系统缓存 → hosts 文件 → DNS 服务器。
    - **浏览器检查缓存**：

      - 如果是强缓存（如 `cache-control: max-age`），直接使用缓存响应，不再发请求。

    ---

    ### ✅ 2. 建立连接阶段（TCP）

    - **TCP 三次握手** 建立连接（如果是 HTTPS，则还涉及 SSL/TLS 握手）：

      - 第一次：客户端发送 SYN。
      - 第二次：服务器回复 SYN + ACK。
      - 第三次：客户端发送 ACK。
    - **HTTPS** 的话，还包括：

      - TLS 证书验证、非对称加密协商密钥（对称加密更快）、建立安全连接。

    ---

    ### ✅ 3. 浏览器发送 HTTP 请求

    - 浏览器构造 HTTP 请求（包括方法、URL、headers、cookies、body 等）。
    - 请求过程中可能会：

      - **携带 Cookie**（保持登录态）。
      - 触发跨域请求（如使用 `CORS`）。
      - 发出多个并发请求（多个资源）。
    - 如果使用的是 HTTP/2，可能会多路复用。

    ---

    ### ✅ 4. 服务器处理请求并返回响应

    - 服务器接收请求，进行逻辑处理（如查询数据库、生成页面）。
    - 返回响应（HTTP 状态码、响应头、响应体 HTML/JSON/CSS/JS 等）。
    - 响应中可能包含：

      - **重定向**（301/302）。
      - **缓存控制**。
      - **Cookie 设置**。
      - **CSP 安全策略**。
      - **内容压缩（gzip、brotli）** 。

    ---

    ### ✅ 5. 浏览器接收响应并渲染页面（关键）

    #### 💡 HTML 解析流程（“构建页面”的核心）：

    1. **解析 HTML**，构建 DOM 树。
    2. 遇到 `<link>`​、`<script>`​、`<img>`​ 等资源标签，发起**并行请求**（遵循优先级）。
    3. **解析 CSS**，构建 CSSOM 树。
    4. DOM + CSSOM 合并为 **渲染树（Render Tree）** 。
    5. **布局（Layout）** ：计算每个节点的大小和位置。
    6. **绘制（Paint）** ：将像素渲染到屏幕上。

    #### ⏱️ 关键性能点：

    - 外链 CSS 会阻塞渲染。
    - ​`<script>`​ 默认阻塞解析，除非加了 `defer/async`。
    - 首次渲染时间（FP、FCP、LCP）是核心性能指标。

    ---

    ### ✅ 6. 执行 JS 和事件绑定

    - JavaScript 执行引擎（V8）开始执行 JS 脚本。
    - JS 会操作 DOM（例如挂载事件）。
    - 加载框架（如 Vue/React）、初始化页面逻辑。

    ---

    ### ✅ 7. 页面交互与异步处理

    - 页面加载完成后，进入用户交互阶段。
    - 浏览器启动事件循环（Event Loop）处理异步任务（如 `setTimeout`​、`fetch`）。
    - 页面可能再发起：

      - **懒加载**（图片、组件）。
      - **请求接口数据（AJAX、fetch）** 。
      - **开启 WebSocket、Service Worker 等技术增强体验**。

    ---

    ### 🌟 总结版（可做结尾）：

    > “从输入 URL 到页面加载完成，是一个涉及 DNS 解析、TCP 连接、请求发送、服务器响应、资源加载、DOM/CSS 解析、页面渲染、JS 执行等多个阶段的完整流程。如果是 HTTPS、SPA 应用，还涉及证书验证、路由控制、懒加载等内容。”
    >

    ---

    如果你时间有限（比如面试官只给你 2 分钟），可以简要说一句话版本：

    > “输入 URL 后，浏览器先进行 DNS 解析获取 IP，通过 TCP（或 TLS）建立连接后发送 HTTP 请求，服务器返回 HTML，浏览器解析 HTML 构建 DOM，加载 CSS 和 JS，构建渲染树，完成布局与绘制，并执行 JS，最终呈现出可交互的页面。”
    >

    ‍

    # 进阶

    ‍

    ## 垃圾回收机制

    1. 引用计数
    2. 标记清除

    ‍

    ## 0.1+0.2！=0.3

    **考察：浮点数精度丢失问题及如何解决**

    原因：数字在底层会被转换成二进制数据保存，

    如 0.1（0.00011011...) 在二进制中是无限循环小数，由于精度限制而截断，导致存储误差。

    ‍

    解决：

    1. 扩大倍数计算
    2. 使用 `.toFixed()`
    3. 使用高精度库：`decimal.js`​、`big.js`​ 或 `bignumber.js`
    4. 转成字符串处理

    ‍

    ‍

    ‍

    ‍

    ‍


[^5]: # Webpack知识总结

    # 基础

    1. 概念：将项目中分散的各类资源（JS、CSS、图片等）视为模块，分析依赖关系后打包成符合生产环境的静态资源。其最核心的功能是**解决模块之间的依赖**。
    2. loader：将非 JS/JSON 文件转换为 Webpack 能识别的 JS 模块。
    3. plugin：**打包过程的扩展**（如优化、资源管理、环境注入等）
    4. 生命周期

       1. ​`beforeRun`：Webpack 进入编译前的阶段，此时会初始化 Compiler 对象。
       2. ​`run`：Webpack 开始编译前的阶段，此时会读取入口文件和依赖，并创建依赖图。
       3. ​`compilation`：Webpack 进入编译阶段，此时会开始编译入口文件和依赖的模块，并生成输出文件。
       4. ​`emit`：Webpack 生成输出文件前的阶段，此时可以在插件中处理生成的输出文件。
       5. ​`done`：Webpack 完成打包后的阶段，此时可以在插件中进行一些清理工作。
    5. [webpack5新特性](https://webpack.js.org/blog/2020-10-10-webpack-5-release/)

       1. **持久化缓存（Persistent Caching）** 。

          1. Webpack 5 内置了**磁盘缓存**。
          2. 通过配置 `cache: { type: 'filesystem' }`​，Webpack 会将构建结果存储在硬盘。二次构建时直接读取缓存，构建速度通常能提升 **80% 以上**。
       2. **模块联邦（Module Federation）**

          1. 拆分应用，共享模块
       3. **改进Tree Shaking**

          1. Tree Shaking是Webpack 5的一个强大功能，通过优化模块依赖关系，消除未使用的代码，从而减小最终生成文件的体积。
       4. ​`optimization`
    6. 常用loader和plugin

       1. loader（右到左、上到下）：

          1. ​**语言转换**​：`ts-loader`​（TS → JS）、`babel-loader`（ES6+ → ES5）；
          2. ​**样式处理**​：`less-loader`​（Less → CSS）、`sass-loader`​（Sass → CSS）、`postcss-loader`（CSS 兼容处理）；
          3. ​**资源处理**​：`file-loader`​（文件拷贝）、`url-loader`（文件转 Base64）；
          4. **模板处理**：`vue-loader`​（解析 Vue 单文件组件）、`pug-loader`（解析 Pug 模板）。
       2. plugin（）：

          1. ​**资源生成**​：`html-webpack-plugin`​（生成 HTML）、`mini-css-extract-plugin`（提取 CSS 为文件）；
          2. ​**代码优化**​：`terser-webpack-plugin`​（压缩 JS）、`css-minimizer-webpack-plugin`（压缩 CSS）；
          3. ​**构建辅助**​：`clean-webpack-plugin`​（​**清理输出目录**​）、`webpack-bundle-analyzer`（分析包体积）；
          4. ​**环境注入**​：`define-plugin`​（注入全局变量）、`copy-webpack-plugin`（拷贝静态资源）；
          5. **热更新**：`webpack-hot-middleware`（热更新中间件）。
    7. **CommonJS和ES Module（ESM）**

       1. **CommonJS（Node.js 标准）**

          1. 值拷贝
          2. require、module.exports
          3. 同步模块
          4. 不支持静态分析
       2. **ES Module（ESM）（浏览器原生支持）**

          1. 值引用
          2. import、export
          3. 支持异步模块
          4. 支持静态分析tree-shaking
       3. 如何解决循环引用问题

          1. **CommonJS：在运行时处理，缓存（Caching）。每个模块只执行一次，执行后被缓存。特点：** 不会无限循环（因为缓存了未执行完的模块）。
          2. **ES Module（ESM）：在编译时处理，静态分析与符号绑定（Bindings）。特点：** 利用延迟执行，模块内代码执行时引用均已绑定。

    ‍

    # 进阶

    1. 构建流程

       1. **依赖解析**：从 `entry`​ 配置的入口文件出发，递归解析 `import/require` 语句，构建「模块依赖图谱」（记录所有模块的依赖关系）；
       2. ​**模块转换**​：通过 `loader`​ 处理非 JS 模块（如 `css-loader`​ 处理 CSS、`babel-loader`​ 转译 ES6+、`file-loader` 处理静态资源），统一转为 JS 模块；
       3. **chunk 生成**：根据 `splitChunks`​ 等配置，将依赖图谱拆分为多个 `chunk`​（代码块），最终输出为 `bundle`（打包文件）。
    2. 优化

       1. 减小打包体积：tree-shaking、代码压缩、按需加载、外部依赖`externals`
       2. 提升构建速度：缓存优化、多线程构建、缩小解析范围、排除无关文件
       3. 优化运行性能：代码分割、预加载/预请求、懒加载
       4. 其他优化：图片优化、作用域提升、生产环境优化
    3. commonjs和esmodule互用？

       1. Webpack 会生成一个​**自定义的模块运行时系统**，模拟 CommonJS 的核心机制：
       2. 定义 `__webpack_require__`​ 函数：替代原生 `require`，负责加载模块、管理模块缓存、处理依赖引用；
       3. 封装模块作用域：每个模块被包裹在独立的匿名函数中，避免全局变量污染，同时为每个模块创建 `module`​/`exports` 对象（模拟 CommonJS 的模块上下文）；
       4. 模块 ID 映射：将文件路径转换为唯一的模块 ID（如 `./math.js` → ID:1），通过 ID 快速查找模块。
       5. ```js
          (function(modules) {
            // Webpack 自定义的 require 函数
            function __webpack_require__(moduleId) {
              var module = { exports: {} };
              modules[moduleId](module, module.exports, __webpack_require__);
              return module.exports;
            }

            // 入口点
            __webpack_require__(0);
          })({
            // 模块定义
            0: function(module, exports, __webpack_require__) {
              var add = __webpack_require__(1).add;
              console.log(add(1, 2));
            },
            1: function(module, exports) {
              function add(a, b) {
                return a + b;
              }
              exports.add = add;
            }
          });
          ```
    4. loader插件编写 **（函数）**

       1. ```js
          // 基础结构
          module.exports = function(source, sourceMap, meta) {
            // source: 输入内容
            // SourceMap 开启source-map可以便于我们在浏览器的开发者工具中查看源码
            // meta: 其他元数据
            return transformedSource; // 返回处理后的字符串
          }
          ```
    5. plugin插件编写 **（类）**

       1. ```js
          class MyPlugin {
            apply(compiler) {
              compiler.hooks.emit.tapAsync('MyPlugin', (compilation, callback) => {
                // 在 emit 阶段处理资源
                console.log('Assets about to emit...');
                callback();
              });
            }
          }

          module.exports = MyPlugin;
          ```
    6. ​`compiler`​、`compilation`

       1. ​`compiler`​：全局唯一的 “编译器”，代表整个 Webpack 构建过程的**生命周期管理者**。
       2. ​`compilation`​：代表**一次具体的构建过程**（如  **“首次构建” 或 “某次热更新构建”** ），负责处理模块、依赖和输出文件的具体逻辑。
    7. devServer跨域问题

       1. **跨域问题是由浏览器的 同源策略 引起的**，而 Webpack Proxy 通过以下方式绕过该限制：
       2. **服务器间通信无跨域限制**

          1. 代理服务器（Webpack Dev Server）和目标服务器（如 API 服务器）之间的通信不受同源策略限制。
       3. **浏览器与代理同源**

          1. 浏览器访问的是本地开发服务器（如 `http://localhost:8080`），与代理服务器同源，因此不会触发跨域限制。
    8. vite和webpack

       1. **vite（esbulid、仅需支持现代浏览器）**

          1. Vite 是​**构建工具 + 开发服务器**，核心基于浏览器原生 ESM 支持（现代浏览器已内置 ESM 加载能力）：
          2. 启动时​**不打包任何代码**​，仅启动一个​**轻量的 Dev Server**；
          3. 当浏览器请求某个模块（比如 `/src/main.js`​）时，​**Vite 才会实时编译该模块及其直接依赖**；
          4. 未被请求的模块（比如某个未打开的页面组件）**永远不会被编译，从根源上减少了启动时的计算量**。特别是在大型项目中，文件数量众多，Vite 的优势更为明显
          5. 预构建：**启动时仅预构建第三方依赖**：Vite 会用 esbuild 将第三方依赖打包成单个 ESM 模块，减少请求数；
       2. webpack（node）

          1. 启动时会从入口文件出发，​**递归解析所有依赖**（包括第三方包、业务代码），构建完整的依赖图；
          2. 将所有模块（无论是否立即使用）​**打包成一个 / 多个 bundle 文件**；
          3. 即使是开发环境，**也必须等全量打包完成后，Dev Server 才能启动**，项目越大，打包时间越长（比如几百 MB 的 node\_modules 都要参与解析）。**会增加启动时间和构建时间。**
    9. ​`Hash`​、`Contenthash`​、`Chunkhash`

       1. ​`Hash`​：和整个项目的构建相关，只要项目有修改（`compilation`​实例改变），`Hash`就会更新）
       2. ​`Contenthash`：和文件的内容有关，只有内容发生改变时才会修改
       3. ​`Chunkhash`​：和**webpack**构架的chunk有关 不同的**entry**会构建出不同的**chunk** （不同 `ChunkHash`之间的变化互不影响）
    10. ​`chunk`：

        1. **Webpack 将一切视为模块（Module），在将模块打包成最终文件（Bundle）时，需要将这些模块按照某种逻辑关系划分为不同的“组”，这些组就是 Chunk。**
        2. 通常情况下一个 Chunk 对应一个 Bundle，但若配置了更复杂的打包规则，一个 Chunk 可能会产生多个 Bundle。


[^6]: # 知识总结

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
    10. 运行时（Runtime）和编译时（Compiler）有什么区别？

        1. **编译时（Compiler）**

           - 主要考察 `.vue` 文件如何转译为浏览器可识别的 JS，以及 Vue 如何在编译期预判代码变化。
        2. **运行时（Runtime）** 

           - 主要考察 `render` 函数执行、Virtual DOM、Patch 算法和响应式系统。
    11. **Vue3 的渲染性能为什么比 Vue2 快？**

        1. 基于 Proxy 的响应式系统，Proxy 直接代理对象无需深层递归；
        2. 运行时配合编译时优化的静态标记，减少了对比不必要的节点。
    12. **Virtual DOM 的原理是什么？**

        1. 运行时通过 JS 对象描述界面结构，在数据变更后生成新旧 VNode，通过 Diff 算法计算最小变化，从而更新真实 DOM。
    13. **Virtual DOM 的优势有哪些？**

        1. 性能提升：避免直接操作真实DOM产生的重排重绘，通过diff算法局部更新提升性能
        2. 跨平台：：虚拟DOM抹平了平台差异，**使Vue可以渲染到Web、移动端（Weex）等**
        3. 数据驱动：开发者只需修改数据，Vue通过组件化机制自动完成DOM的更新，开发者专注于业务逻辑。
    14. **虚拟DOM的diff算法（对比过程）是怎样的？**

        1. 同级比较，深度遍历子元素对比
        2. Vue通过新旧两棵虚拟DOM树进行同层级比较（patch）。它采用深度优先遍历，对比节点的标签、属性、文本内容，并结合Key值，找出需要修改的最小差异，最后应用到真实DOM上。

    ‍


[^7]: # 笔试题

    参考：

    1. [【前端手写】全面考察基础的23道经典笔试题](https://juejin.cn/post/7270870135228727356#heading-9)

    # 总结

    1. 实现异步请求并发数控制（考察[Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled).resolve, .allSettled, .race, .any, .all, .reject, .try等）
    2. deepClone,考察递归以及适用instanceof，typeof，Object.prototype.toString.call，weakMap，weakSet等循环引用问题
    3. 科里化函数（curry）
    4. 洋葱模型（Koa），async/await 语法和函数递归。
    5. new 一个对象原理
    6. instanceof，考察对象的原型 obj.__proto__ == Function.prototype;  [Object.getPrototypeOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)
    7. 实现发布订阅模式
    8. 实现call，bind，apply
    9. 链式调用实现，考察return this。
    10. 实现防抖（debounce）：一秒内多次请求，只有最后一次生效 --- 输入停止了再说话；
    11. 节流（throttle）：一秒内多次请求，只有最初的生效 --- 固定节奏说话
    12. 递归实现中序遍历（栈，先进后出）
    13. 斐波那契数列和尾递归
    14. 数组去重: `Array.from(new Set([1,2,3,1,2,3]))`
    15. 实现`once`函数
    16. 考察对象函数：

        1. [Array](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/every)：.from, .indexof, .concat, .entries, .every, .some, .find, .findIndex, .shift, .pop, .includes, .splice, .slice, .flat
        2. [Set](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set/Set)集合： .add, .delete, .clear, .has, .entries, .keys, .values, .size
        3. [Map](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map/Map)字典： .set, .delete, .clear, .get, .has, .keys, .values, .size
    17. ​`for...of`​, `for...in`

        1. ​`for...of`​: 数组，“**of 值 value**” → 遍历的是**值内容**。
        2. ​`for...in`​: 对象，“**in 键 key**” → 遍历的是**键名**。
    18. 排序算法和复杂度

        1. 冒泡排序：O(n^2)
        2. 快速排序：
    19. 数组转树，树转数组

    ‍

    # 复习内容

    #### new一个对象原理

    ```js
    function myNew(func, ...args) {
    	const obj = Object.create(func.prototype)
    	const result = func.apply(obj, args)
    	return result !== null && typeof result === 'object' ? result : obj
    }
    ```
    #### 1. 使用Promise实现每隔1秒输出1,2,3

    ```js
    const arr = [1, 2, 3]
    arr.reduce((p, x) => {
      return p.then(() => {
        return new Promise(r => {
          setTimeout(() => r(console.log(x)), 1000)
        })
      })
    }, Promise.resolve())
    ```
    #### 使用Promise实现红绿灯交替重复亮

    ```js
    function red() {
      console.log("red");
    }
    function green() {
      console.log("green");
    }
    function yellow() {
      console.log("yellow");
    }
    const light = function (timer, cb) {
      return new Promise(resolve => {
        setTimeout(() => {
          cb()
          resolve()
        }, timer)
      })
    }
    const step = function () {
     return Promise.resolve()
       .then(() => light(1000, red))
       .then(() =>  light(1000, green))
       .then(() =>  light(1000, yellow))
       .then(() => step())
    }

    step();
    ```
    ‍

    #### Koa洋葱模型compose

    ```js
    function compose(middlewares) {
      return function (context) {
        return dispatch(0); // 从第一个中间件开始

        function dispatch(i) {
          if (i >= middlewares.length) return Promise.resolve();
          const fn = middlewares[i];
          return Promise.resolve(
            fn(context, () => dispatch(i + 1)) // next 为下一个中间件的调用
          );
        }
      };
    }

    ```
    #### 实现Promise

    ```js
    class MyPromise {
        static PENDING = 'pending';
        static FULFILLED = 'fulfilled';
        static REJECTED = 'rejected';
        constructor(exector) {
            this.value = null
            this.status = MyPromise.PENDING;
            this.onFulfilledCallbacks = [];
            this.onRejectedCallbacks = [];
            const resolve = (value) => {
                if (this.status == MyPromise.PENDING) {
                    this.status = MyPromise.FULFILLED;
                    this.value = value;
                    this.onFulfilledCallbacks.forEach(r => r(value))
                }
            }
            const reject = (reason) => {
                if (this.status = MyPromise.PENDING) {
                    this.status = MyPromise.REJECTED;
                    this.value = reason;
                    this.onRejectedCallbacks.forEach(r => r(reason))
                }
            }
            try {
                exector(resolve, reject);
            } catch (error) {
                reject(error);
            }
        }
        then(onFulfilled, onRejected) {
            return new MyPromise((resolve, reject) => {
                if (this.status === MyPromise.FULFILLED) {
                    setTimeout(() => {
                        try {
                            onFulfilled && resolve(onFulfilled(this.value));
                        } catch (error) {
                            reject(error);
                        }
                    });
                } else if (this.status == MyPromise.REJECTED) {
                    setTimeout(() => {
                        try {
                            onRejected && resolve(onRejected(this.value));
                        } catch (error) {
                            reject(error)
                        }
                    })
                } else if (this.status == MyPromise.PENDING) {
                    this.onFulfilledCallbacks.push(() => {
                        setTimeout(() => {
                            try {
                                onFulfilled && resolve(onFulfilled(this.value));
                            } catch (error) {
                                reject(error);
                            }
                        });
                    })
                    this.onRejectedCallbacks.push(() => {
                        setTimeout(() => {
                            try {
                                onRejected && resolve(onRejected(this.value));
                            } catch (error) {
                                reject(error);
                            }
                        });
                    })
                }
            })
        }
        catch(onRejected) {
            return this.then(null, onRejected);
        }
        finally(callback) {
            return this.then(
                value => MyPromise.resolve(callback()).then(() => value),
                reason => MyPromise.resolve(callback()).then(() => { throw reason; })
            );
        }
        static resolve(value) {
            return new MyPromise((resolve) => {
                resolve(value);
            });
        }
        static reject(reason) {
            return new MyPromise((resolve, reject) => {
                reject(reason);
            });
        }
        static race(promises) {
            return new MyPromise((resolve, reject) => {
                promises.forEach(p => {
                    p.then(resolve, reject);
                });
            });
        }
        static all(promises) {
            return new MyPromise((resolve, reject) => {
                const result = [];
                let count = 0;
                promises.forEach((p, index) => {
                    p.then(value => {
                        result[index] = value;
                        count++;
                        if (count === promises.length) {
                            resolve(result);
                        }
                    }, reject);
                });
            })
        }
        static allSettled(promises) {
            return new MyPromise((resolve, reject) => { 
                const result = [];
                let count = 0;
                promises.forEach((p, index) => {
                    p.then(value => {
                        result[index] = { status: 'fulfilled', value };
                    }, reason => {
                        result[index] = { status: 'rejected', reason };
                    }).finally(() => {
                        count++;
                        if (count === promises.length) {
                            resolve(result);
                        }
                    });
                });
            })
        }
        static any(promises) {
            return new MyPromise((resolve, reject) => {
                const errors = [];
                let count = 0;
                promises.forEach((p, index) => {
                    p.then(resolve)
    				.catch(reason => {
                        count++;
                        if (count === promises.length) {
                            reject(new AggregateError(errors, 'All promises were rejected'));
                        }
                    });
                });
            });
        }
    }
    ```
    ‍

    #### 数组转树，树转数组

    ```js
    let input = [
      {
        id: 1,
        val: "学校",
        parentId: null,
      },
      {
        id: 2,
        val: "班级1",
        parentId: 1,
      }
    ]
    const arrayToTree = (arr) => {
        const map = {};
        const result = [];
        arr.forEach(e => {
            map[e.id] = { ...e, children: [] };
        })
        arr.forEach((e) => {
            if(e.parentId === null) {
                result.push(map[e.id]);
            } else
                map[e.parentId]?.children.push(map[e.id]);
        })
        return result[0]
    }
    const treeToArray = (tree) => {
        const result = [];
        const stack = [tree];
        while(stack.length) {
            const node = stack.pop();
            result.push({...node, children: undefined});
            stack.push(...(node.children || []));
        }
        return result;
    }
    ```
    ‍

    #### 防抖和节流

    ```js
    // 防抖
    const debounce = (fn, delay) => {
    	let timer = null
    	return function(...args) {
    		clearTimeout(timer);
    		timer = setTimeout(() => {
    			fn.apply(this, args)
    		}, delay)
    	}
    }
    // 节流
    const throttle = (fn, delay) => {
    	let last = 0;
    	return function(...args) {
    		let now = Date.now();
    		if(now - last >= delay){
    			fn.apply(this, args)
    			last = now
    		}
    	}
    }
    ```
    ‍

    #### 柯里化函数

    ```js
    const curry = (fn) => {
        const len = fn.length;
        return function curryFn(...args) {
            if (args.length >= len) {
                fn.apply(this, args)
            } else {
                return curryFn.bind(this, ...args)
            }
        }
    }
    ```
    #### 数组扁平化flatten

    ```js
    const flatten = (arr) => {
    	const result = [];
    	arr.forEach(e => {
    		if(Array.isArray(e)){
    			result.push(...flatten(e))
    		} else {
    			result.push(e)
    		}
    	})
    	return result
    }
    ```
    ‍

    #### 封装图片加载js

    ```js
    const loadImage = (url) => {
        return new Promise((resolve, reject) => {
            const img = new Image()
            img.src = url
            img.onload = () => {
                resolve(img);
            }
            img.onerror = () => {
                reject(new Error(`Failed to load image at ${url}`));
            }
        })
    }
    ```
    ‍

    #### 控制并发数量

    ```js
    const limitLoad = (arr, limit) => {
        let index = 0;
        const results = [];
        let finishedCount = 0;

        const load = async () => {
            const nextIndex = index++;
            if (nextIndex >= arr.length) return;

            try {
                const fn = arr[nextIndex]; // 假设 arr 是一个函数数组
                const res = await fn(); // 假设 fn 是一个返回 Promise 的函数
                results[nextIndex] = res;
            } catch (error) {
                results[nextIndex] = error;
            } finally {
                finishedCount++;
                if (index < arr.length) {
                    load();
                } else if (finishedCount === arr.length) {
                    console.log('All tasks completed:', results);
                }
            }
        };

        for (let i = 0; i < Math.min(limit, arr.length); i++) {
            load();
        }
    }
    ```
    #### 实现once函数

    ```js
    const once = (fn) => {
        let finish = false;
        let result = null;
        return function (...args) {
            if (finish) return result;
            finish = true;
            result = fn.apply(this, args);
            return result
        };
    }
    ```
    #### 斐波那契数列

    ```js
    const map = new Map([[0,0], [1, 1], [2, 1]]);
    const fibo = (n) => {
    	if(n == 0) return 0
    	else if(n <= 2) return 1
    	if(map.has(n)) return map.get(n)
    	else {
    		const result = fibo(n-1) + fibo(n - 2)
    		map.set(n, result)
    		return result
    	}
    }
    ```
    #### 括号匹配

    ```js
    const strMap = (str) => {
    	const arr = str.trim().split('').filter(e => !!e)
    	const stack = [];
    	for(let i = 0; i < arr.length; i++){
    		const c = arr.at(i)
    		if(c == '(' || c == '[' || c == '{') {
    			stack.push(c)
    		} else {
    			let tempStack = []
    			while(stack.length) {
    				let cur = stack.pop();
    				if((cur == '(' && c == ')') || (cur == '[' && c == ']') || (cur == '{' && c == '}')) {
    					break
    				} else {
    					tempStack.push(cur)
    				}
    			}
    			while(tempStack.length) {
    				stack.push(tempStack.pop())
    			}
    		}
    	}
    	return stack.length === 0
    }
    ```
    #### deepClone

    ```js
    function deepClone(obj, cache = new WeakMap()) {
      if (obj === null || typeof obj !== 'object') return obj;

      if (obj instanceof Date) return new Date(obj);
      if (obj instanceof RegExp) return new RegExp(obj);
      if (typeof obj === 'function') return obj;

      if (cache.has(obj)) return cache.get(obj); // 🧠 处理循环引用

      const clone = Array.isArray(obj) ? [] : {};
      cache.set(obj, clone); // 🔁 缓存当前对象

      for (let key in obj) {
        if (obj.hasOwnProperty(key)) {
          clone[key] = deepClone(obj[key], cache);
        }
      }
      return clone;
    }

    ```
    #### bind，call，apply实现

    ```js
    Function.prototype.myBind = function(ctx, ...args) {
      ctx = ctx || window;
      const key = Symbol();
      ctx[key] = this;
      return function(...args2) {
        const result = ctx[key](...args, ...args2);
        delete ctx[key];
        return result;
      };
    };
    Function.prototype.myCall = (ctx, ...args) => {
    	ctx = ctx || window;
    	const key = Symbol();
    	ctx[key] = this;
    	const result = ctx[key](...args);
    	delete ctx[key];
    	return result;
    }
    Function.prototype.myApply = (ctx, args) => {
    	ctx = ctx || window;
    	const key = Symbol();
    	ctx[key] = this;
    	const result = ctx[key](args);
    	delete ctx[key];
    	return result;
    }
    ```
    #### LRU（最近最少使用）实现

    ```js
    class LRUCache {
    	constructor(maxNum) {
    		this.maxNum = maxNum
    		this.cached = new Map(); // Map字典有序
    	}
    	get(key) {
    		if(this.cached.has(key)) {
    			let temp = this.cached.get(key)
    			this.cached.delete(key)
    			this.cached.set(key,temp)
    			return temp;
    		}
    		return -1
    	}
    	put(key, value) {
    		if(this.cached.has(key)) {
    			this.cached.delete(key)
    			this.cached.set(key, value)
    		}
    		if(this.maxNum < this.cached.size) {
    			// 删除最开始添加的元素
    			this.cached.delete(this.cached.keys().next().value)
    		}
    	}
    }
    ```
    #### 反转链表

    ```js
    function reverseLink(head) {
    	let curr = head;
    	let prev = null;
    	while(curr) {
        	const next = curr.next; // 暂存下一个节点
    	    curr.next = prev;       // 当前指针反转
    	    prev = curr;            // 前进 prev
    	    curr = next;            // 前进 curr
    	}
     	return prev;
    }
    ```
    ‍

    #### 回文字符串判断（双指针）

    ```js
    function isPalindrome(str) {
    	let startIdx= 0, endIdx = str.length - 1;
    	while(startIdx != endIdx) {
    		if(str[startIdx] != str[endIdx]) return false
    		startIdx++;
    		endIdx--;
    	}
    	return true;
    }
    ```
    #### 字符串最长不重复子串（滑动窗口）

    ```js
    function lengthOfLongestSubstring(str) {
    	let left = 0, max = 0, set = new Set();
    	for(let right = 0; right < str.length; right++) {
    		while(set.has(str[right])) set.delete(str[left++]);
    		set.add(str[right]);
    		max = Math.max(set.size, max)
    	}
    	return max
    }
    ```
    #### 合并两个有序数组

    ```js
    const mergeArray = (arr1, arr2) => {
    	const result = [];
    	let i =0, j = 0;
    	while(i < arr1.length && j < arr2.length) {
    		if(arr1[i] < arr2[j]) {
    			result.push(arr1[i]);
    			i++;
    		} else {
    			result.push(arr2[j]);
    			j++;
    		}
    	}
    	while(i < arr1.length) {result.push(arr1[i]);i++;}
    	while(j < arr2.length) {result.push(arr2[j]);j++;}
    	return result
    }
    ```
    #### 实现instanceof

    ```js
    function myInstanceof(current, target) {
    	let _proto = Object.getPrototypeOf(current);
    	const targetProto = target.prototype
    	while(_proto) {
    		if(_proto === targetProto) return true
    		_proto = Object.getPrototypeOf(_proto);
    	}
    	return false
    }
    ```
    #### 计算两个数组的补集

    ```js
    补集：如果 b 是 a 的子集，返回存在于 a 不存在于 b 的元素集合，反之返回空集合
    function getBu(arr1, arr2) {
    	let a = new Set(a);
    	let b = new Set(b);
    	let res = [...arr1.filter(e => !b.has(e)), ...arr2.filter(e => !a.has(e))]
    	if(res.length === arr1.length + arr2.length) return [];
    	return res
    }
    ```
    #### **函数生成器**

    ```js
    // 我们要实现一个函数 reorderArgs(fn, indices)，它：
    //  接收两个参数：
    //  	fn: 原函数
    //		indices: 一个数组，表示新函数的参数应如何映射到原函数参数
    //	返回一个新函数 newFn
    //  调用 newFn(...args) 时，将 args 中的参数按照 indices 指定的顺序传给 fn
    function reorderArgs(fn, indices) {
      return function(...args) {
        const reorderedArgs = indices.map(i => args[i]);
        return fn(...reorderedArgs);
      };
    }
    ```
    #### BFS（广度优先搜索）和DFS（深度优先搜索）

    ```js
    function bfsSearch(tree, value) {
    	// 队列
    	let searchNode = null
    	const queue = [tree];
    	while(queue.length) {
    		const node = queue.shift();
    		if(node.value === value) {
    			searchNode = node;
    			break
    		}
    		if(node.left) queue.push(node.left);
    		if(node.right) queue.push(node.right);
    	}
    	return searchNode;
    }
    function dfsSearch(tree, value) {
    	// 栈
    	let searchNode = null;
    	const stack = [tree];
    	while(stack.length) {
    		const node = stack.pop();
    		if(node.value === value) {
    			searchNode = node;
    			break
    		}
    		if(node.right) stack.push(node.right);
    		if(node.left) stack.push(node.left);
    	}
    	return searchNode;
    }
    ```
    #### 排序算法

    ```js
    // 冒泡排序
    // 时间复杂度：O(n^2)
    // 空间复杂度：O(1)
    // 最好： O(n)；最坏：O(n^2)
    // ✅ 稳定
    function bubbleSort(arr) {
    	for(let i = 0; i < arr.length - 1; i++) {
    		let hasSwap = false;
    		for(let j = 0; j < arr.length - 1 - i; j++) {
    			if(arr[j] > arr[j + 1]) {
    				hasSwap = true
    				[arr[j], arr[j+1]] = [arr[j+ 1], arr[j]]
    			}
    		}
    		if(!hasSwap) break
    	}
    	return arr
    }

    // 选择排序
    // 时间复杂度：O(n^2) 
    // 空间复杂度：O(1)
    // 最好： O(n^2)；最坏：O(n^2)
    // ❌ 不稳定
    function selectionSort(arr) {
    	for (let i = 0; i < arr.length - 1; i++) {
    		let minIndex = i;
    		for (let j = i + 1; j < arr.length; j++) {
    			if (arr[j] < arr[minIndex]) {
    				minIndex = j;
    			}
    		}
    		if (minIndex !== i) {
    			[arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    		}
    	}
    	return arr;
    }

    // 插入排序
    // 时间复杂度：O(n^2) 
    // 空间复杂度：O(1)
    // 最好： O(n)；最坏：O(n^2)
    // ✅ 稳定
    function insertSort(arr) {
    	for (let i = 1; i < arr.length; i++) {
    		let key = arr[i];
    		let j = i - 1;
    		while (j >= 0 && arr[j] > key) {
    			arr[j + 1] = arr[j];
    			j--;
    		}
    		arr[j + 1] = key;
    	}
    	return arr;
    }

    // 快速排序
    // 时间复杂度：O(nlogn) 
    // 空间复杂度：O(n)
    // 最好： O(n log n)；最坏：O(n²)
    // ❌ 不稳定
    function quickSort(arr) {
    	if (arr.length <= 1) return arr;
    	const pivot = arr[Math.floor(arr.length / 2)];
    	const left = arr.filter(x => x < pivot);
    	const middle = arr.filter(x => x === pivot);
    	const right = arr.filter(x => x > pivot);
    	return [...quickSort(left), ...middle, ...quickSort(right)];
    }

    // 归并排序
    // 时间复杂度：O(nlogn) 
    // 空间复杂度：O(n)
    // 最好： O(n log n)；最坏：O(n log n)
    // ✅ 稳定
    function mergeSort(arr) {
    	if (arr.length <= 1) return arr;

    	const mid = Math.floor(arr.length / 2);
    	const left = mergeSort(arr.slice(0, mid));
    	const right = mergeSort(arr.slice(mid));
    	function merge(left, right) {
    		const result = [];
    		let i = 0, j = 0;
    	
    		while (i < left.length && j < right.length) {
    			if (left[i] < right[j]) {
    				result.push(left[i++]);
    			} else {
    				result.push(right[j++]);
    			}
    		}
    		return result.concat(left.slice(i)).concat(right.slice(j));
    	}
    	return merge(left, right);
    }

    // 原生排序
    // 时间复杂度：O(nlogn) 
    // 空间复杂度：O(log n)~O(n)
    // ❌ 不稳定
    arr.sort((a, b) => a - b)
    ```
    ‍


[^8]: # 知识总结

    # 基础

    1. HTTP状态码

       1. 1XX：消息状态码（100： Continue 继续）
       2. 2XX：成功状态码（200：OK 请求成功； 201：Created 已创建）
       3. 3XX：重定向状态码（301: 永久重定向； 302: 临时重定向； 304: 资源未修改（协商缓存）； ）
       4. 4XX：客户端错误状态码（400: 客户端的请求有问题； 401: 需要认证的用户； 403: 服务器拒绝请求； 404: 资源不存在； ）
       5. 5XX：服务端错误状态码（500: 服务器内部出错； 501: 服务器不支持此请求； ）
    2. [HTTP连接基础与过程](https://www.google.com/search?q=HTTP%E8%BF%9E%E6%8E%A5%E5%9F%BA%E7%A1%80%E4%B8%8E%E8%BF%87%E7%A8%8B&sca_esv=0555e3765a0d8a6a&biw=1601&bih=898&sxsrf=ANbL-n6fAdV2oq6w1z4FRyZ_8qFaWt03nA%3A1772723245059&ei=LZypac6XA6bc2roPrvjM4Qo&ved=2ahUKEwj2kbzkhImTAxXPsVYBHaTNKXIQgK4QegQIAxAA&uact=5&oq=http%E8%BF%9E%E6%8E%A5%E8%BF%87%E7%A8%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E9%97%AE%E4%BB%80%E4%B9%88&gs_lp=Egxnd3Mtd2l6LXNlcnAiImh0dHDov57mjqXov4fnqIvpnaLor5Xpopjpl67ku4DkuYgyBRAAGO8FMgUQABjvBTIFEAAY7wVIox1QAFiRG3AAeACQAQCYAdoBoAHcE6oBBjAuMTYuMbgBA8gBAPgBAZgCCKACkQnCAggQABiABBiiBMICDBAhGKABGMMEGAoYKsICChAhGKABGMMEGAqYAwCSBwUwLjcuMaAH1DOyBwUwLjcuMbgHkQnCBwUwLjUuM8gHFYAIAA&sclient=gws-wiz-serp&mstk=AUtExfBeE0QY9CdMOJnCMZoafqvm-HYbC2Z2etXVzU7uj85YK7AP5_DFD1DY2fAM-fPeaW7lipEbzNBgzFmVb96t-YbcTqzaWln60KYSh7zqk-Fh4RkK97dJmmr1LufaU8DATO8rj1e-UaaVHLks3gH9RQpf_2Ub_wZicg9dPaGmp2-CpR_TWYGRBXXAfs5rRVUS5Jr-arMwyLH_1QpBbwINZ9cXAwppTF2lkRZ0cmToMuWVHwO-2HkDz5BmzPvpXMCiQEnUkYxz75zld2b6qxmBkHJR0ucKgIVv2zulfpiOgXdu4xuzHLpxP4K-QOmjj5ioFwerWYKnx-AcpYR9umLjD2gr0tJXLxkvREXynDe6KrZ-38GEiD0rqSuzMU36io5RpHyNybTIXTZydoQF9kVngybUEDEFIs3zJ2sE-lGY8JlqAjL65Sd83GgDyLVVqhAZ20sG0vxvmXmmyrKj7wp_VraoQwQZB9CPvCW-l3GDZQ&csui=3)

       1. **输入URL后发生的全过程**：DNS解析、TCP连接、发送HTTP请求、服务器处理、服务器返回响应、页面渲染、TCP断开。
       2. **TCP三次握手**：为何需要三次？（确认双方收发能力）。
       3. **TCP四次挥手**：为何需要四次？（确保数据传输完毕）。
       4. **长连接与短连接**：HTTP 1.1 `Keep-Alive` 的作用是什么？
    3. Http和Https

       1. ​**HTTP与HTTPS的区别**：明文传输与SSL/TLS加密。
       2. ​**HTTPS的TLS握手过程**：如何交换密钥？（客户端随机数、服务器证书、预主密钥）。
       3. ​**CA证书验证**：浏览器如何验证证书合法性？。
       4. ​**对称加密与非对称加密**：分别在HTTPS的什么阶段使用？
    4. Http1、Http2、Http3

       1. ​**1.1**: 持久连接、管道化。
       2. ​**2.0**: 多路复用、头部压缩、服务器推送。
       3. **3.0**: 基于UDP的QUIC协议，解决队头阻塞
    5. 强缓存和协商缓存

       1. 强缓存：在有效时间内，不会向服务器发送请求，直接从缓存中读取资源。控制强制缓存的字段分别是Expires和Cache-Control，其中Cache-Control的优先级高于Expires。
       2. 协商缓存：当强制缓存失效后，浏览器会携带缓存标识向服务器发起请求，由服务器根据缓存标识决定是否使用缓存。控制协商缓存的字段有Last-Modified/If-Modified-Since和Etag/If-None-Match。

    # 进阶

    ‍


[^9]: # 前端基建

    # 基建

    1. 工程化工具
    2. 代码规范管理
    3. 组件库与业务沉淀
    4. 性能优化
