# 前端基础和底层原理

对于前端的学习和提高，我的基本思路是这样的。首先，前端的三个最基本的东西 HTML 5、CSS 3 和 JavaScript（ES6）是必须要学好的。这其中有很多很多的技术，比如，CSS 3 引申出来的 Canvas（位图）、SVG（矢量图） 和 WebGL（3D 图），以及 CSS 的各种图形变换可以让你做出非常丰富的渲染效果和动画效果。

ES6 简直就是把 JavaScript 带到了一个新的台阶，JavaScript 语言的强大，大大释放了前端开发人员的生产力，让前端得以开发更为复杂的代码和程序，于是像 React 和 Vue 这样的框架开始成为前端编程的不二之选。

我一直认为学习任何知识都要从基础出发，所以这篇文章我会着重介绍基础知识和基本原理，尤其是如下的这些知识，都是前端程序员需要花力气啃下来的硬骨头。

* **JavaScript 的核心原理**。这里我会给出好些网上很不错的讲 JavaScript 的原理的文章或图书，你一定要学好语言的特性，并且详细了解其中的各种坑。

* **浏览器的工作原理**。这也是一块硬骨头，我觉得这是前端程序员需要了解和明白的关键知识点，不然，你将无法深入下去。

* **网络协议 HTTP**。也是要着重了解的，尤其是 HTTP/2，还有 HTTP 的几种请求方式：短连接、长连接、Stream 连接、WebSocket 连接。

* **前端性能调优**。有了以上的这些基础后，你就可以进入前端性能调优的主题了，我相信你可以很容易上手各种性能调优技术的。

* **框架学习**。我只给了 React 和 Vue 两个框架。就这两个框架来说，Virtual DOM 技术是其底层技术，组件化是其思想，管理组件的状态是其重点。而对于 React 来说，函数式编程又是其编程思想，所以，这些基础技术都是你需要好好研究和学习的。

* **UI 设计**。设计也是前端需要做的一个事，比如像 Google 的 Material UI，或是比较流行的 Atomic Design 等应该是前端工程师需要学习的。

而对于工具类的东西，这里我基本没怎么涉及，因为本文主要还是从原理和基础入手。那些工具我觉得都很简单，就像学习 Java 我没有让你去学习 Maven 一样，因为只要你去动手了，这种知识你自然就会获得，我们还是把精力重点放在更重要的地方。

下面我们从前端基础和底层原理开始讲起。先来讲讲 HTML5 相关的内容。

## HTML 5

HTML 5 主要有以下几本书推荐。

* [HTML 5 权威指南](https://book.douban.com/subject/25786074/) ，本书面向初学者和中等水平 Web 开发人员，是牢固掌握 HTML 5、CSS 3 和 JavaScript 的必读之作。书看起来比较厚，是因为里面的代码很多。
* [HTML 5 Canvas 核心技术](https://book.douban.com/subject/24533314/) ，如果你要做 HTML 5 游戏的话，这本书必读。

对于 SVG、Canvas 和 WebGL 这三个对应于矢量图、位图和 3D 图的渲染来说，给前端开发带来了重武器，很多 HTML5 小游戏也因此蓬勃发展。所以，你可以学习一下。

学习这三个技术，我个人觉得最好的地方是 MDN。

* [SVG: Scalable Vector Graphics](https://developer.mozilla.org/en-US/docs/Web/SVG)
* [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API?retiredLocale=kab)
* [The WebGL API: 2D and 3D graphics for the web](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)

最后是几个资源列表。

* [Awesome HTML5](https://github.com/diegocard/awesome-html5) 。GitHub 上的 Awesome HTML5，其中有大量的资源和技术文章。
* [Awesome SVG](https://github.com/willianjusten/awesome-svg)
* [Awesome Canvas](https://github.com/raphamorim/awesome-canvas)
* [Awesome WebGL](https://github.com/sjfricke/awesome-webgl)

## CSS

在《程序员练级攻略》系列文章最开始，我们就推荐过 CSS 的在线学习文档，这里再推荐一下 [MDN Web Doc - CSS](https://developer.mozilla.org/zh-CN/docs/Web/CSS) 。我个人觉得只要你仔细读一下文档，CSS 并不难学。绝大多数觉得难的，一方面是文档没读透，另一方面是浏览器支持的标准不一致。所以，学好 CSS 最关键的还是要仔细地读文档。

之后，在写 CSS 的时候，你会发现，你的 CSS 中有很多看起来相似的东西。你的 DRY - Don’t Repeat Yourself 洁癖告诉你，这是不对的。所以，你需要学会使用 [LESS](https://lesscss.org/) 和 [SaSS](https://sass-lang.com/) 这两个 CSS 预处理工具，其可以帮你提高很多效率。

然后，你需要学习一下 CSS 的书写规范，前面的《程序员修养》一文中提到过一些，这里再补充几个。

* [Principles of writing consistent, idiomatic CSS](https://github.com/necolas/idiomatic-css)

* [Opinionated CSS styleguide for scalable applications](https://github.com/grvcoelho/css-styleguide)

* [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)

如果你需要更有效率，那么你还需要使用一些 CSS Framework，其中最著名的就是 Twitter 公司的 [Bootstrap](https://getbootstrap.com/)，其有很多不错的 UI 组件，页面布局方案，可以让你非常方便也非常快速地开发页面。除此之外，还有，主打清新 UI 的 [Semantic UI](https://semantic-ui.com/) 、主打响应式界面的 [Foundation](https://get.foundation/) 和基于 Flexbox 的 [Bulma](https://bulma.io/)。

当然，在使用 CSS 之前，你需要把你浏览器中的一些 HTML 标签给标准化掉。所以，推荐几个 Reset 或标准化的 CSS 库：[Normalize](https://github.com/necolas/normalize.css)、[MiniRest.css](https://github.com/jgthms/minireset.css)、[sanitize.css](https://github.com/csstools/sanitize.css) 和 [unstyle.css](https://github.com/Martin-Pitt/css-unstyle)。

关于更多的 CSS 框架，你可以参看[Awesome CSS Frameworks](https://github.com/troxler/awesome-css-frameworks) 上的列表。

接下来，是几个公司的 CSS 相关实践，供你参考。

* [CodePen’s CSS](https://codepen.io/chriscoyier/post/codepens-css)

* [Github 的 CSS](https://markdotto.com/2014/07/23/githubs-css/)

* [Medium’s CSS is actually pretty f***ing good](https://medium.com/@fat/mediums-css-is-actually-pretty-fucking-good-b8e2a6c78b06)

* [CSS at BBC Sport](https://medium.com/bbc-design-engineering/css-at-bbc-sport-part-1-bab546184e66)

* [Refining The Way We Structure Our CSS At Trello](https://blog.trello.com/refining-the-way-we-structure-our-css-at-trello)

最后是一个可以写出可扩展的 CSS 的阅读列表 [A Scalable CSS Reading List](https://github.com/davidtheclark/scalable-css-reading-list) 。

## JavaScript

下面是学习 JavaScript 的一些图书和文章。

* [JavaScript: The Good Parts](https://book.douban.com/subject/11874748/) ，中文翻译版为《JavaScript 语言精粹》。这是一本介绍 JavaScript 语言本质的权威图书，值得任何正在或准备从事 JavaScript 开发的人阅读，并且需要反复阅读。学习、理解、实践大师的思想，我们才可能站在巨人的肩上，才有机会超越大师，这本书就是开始。

* [Secrets of the JavaScript Ninja](https://book.douban.com/subject/26638316/) ，中文翻译版为《JavaScript 忍者秘籍》，本书是 jQuery 库创始人编写的一本深入剖析 JavaScript 语言的书。适合具备一定 JavaScript 基础知识的读者阅读，也适合从事程序设计工作并想要深入探索 JavaScript 语言的读者阅读。这本书有很多晦涩难懂的地方，需要仔细阅读，反复琢磨。

* [Effective JavaScript](https://book.douban.com/subject/25786138/) ，Ecma 的 JavaScript 标准化委员会著名专家撰写，作者凭借多年标准化委员会工作和实践经验，深刻辨析 JavaScript 的内部运作机制、特性、陷阱和编程最佳实践，将它们高度浓缩为极具实践指导意义的 68 条精华建议。

* 接下来是 ES6 的学习，这里给三个学习手册源。
  * [ES6 in Depth](https://hacks.mozilla.org/category/es6-in-depth/)，InfoQ 上有相关的中文版 - [ES6 深入浅出](https://www.infoq.cn/)。还可以看看 [A simple interactive ES6 Feature list](https://codetower.github.io/es6-features?utm_source=mybridge&utm_medium=email&utm_campaign=read_more) ，或是看一下 [阮一峰翻译的 ES6 的教程](https://es6.ruanyifeng.com/) 。
  * [ECMAScript 6 Tools](https://github.com/addyosmani/es6-tools) ，这是一堆 ES6 工具的列表，可以帮助你提高开发效率。
  * [Modern JS Cheatsheet](https://mbeaudru.github.io/modern-js-cheatsheet/) ，这个 Cheatsheet 在 GitHub 上有 1 万 6 千颗星，你就可见其影响力了。

* 然后，还有一组很不错的《[You Don’t Know JS 系列](https://github.com/getify/You-Dont-Know-JS)》 的书。
  * [You Don’t Know JS: “Up & Going”](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20&%20going/README.md#you-dont-know-js-up--going)
  * [You Don’t Know JS: “Scope & Closures”](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20&%20closures/README.md#you-dont-know-js-scope--closures)
  * [You Don’t Know JS: “this & Object Prototypes”](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20&%20object%20prototypes/README.md#you-dont-know-js-this--object-prototypes)
  * [You Don’t Know JS: “Types & Grammar”](https://github.com/getify/You-Dont-Know-JS/blob/master/types%20&%20grammar/README.md#you-dont-know-js-types--grammar)
  * [You Don’t Know JS: “Async & Performance”](https://github.com/getify/You-Dont-Know-JS/blob/master/async%20&%20performance/README.md#you-dont-know-js-async--performance)
  * [You Don’t Know JS: “ES6 & Beyond”](https://github.com/getify/You-Dont-Know-JS/blob/master/es6%20&%20beyond/README.md#you-dont-know-js-es6--beyond)

* 接下来是一些和编程范式相关的文章。
  * [Glossary of Modern JavaScript Concepts: Part 1](https://auth0.com/blog/glossary-of-modern-javascript-concepts/) ，首先推荐这篇文章，其中收集了一些编程范式方面的内容，比如纯函数、状态、可变性和不可变性、指令型语言和声明式语言、函数式编程、响应式编程、函数式响应编程。
  * [Glossary of Modern JavaScript Concepts: Part 2](https://auth0.com/blog/glossary-of-modern-javascript-concepts-part-2/) ，在第二部分中主要讨论了作用域和闭包，数据流，变更检测，组件化……

* 下面三篇文章是德米特里·索什尼科夫（Dmitry Soshnikov）个人网站上三篇讲 JavaScript 内在的文章。
  * [JavaScript. The Core: 2nd Edition](http://dmitrysoshnikov.com/ecmascript/javascript-the-core-2nd-edition/)
  * [JavaScript. The Core (older ES3 version)](http://dmitrysoshnikov.com/ecmascript/javascript-the-core/)
  * [JS scope: static, dynamic, and runtime-augmented](https://codeburst.io/js-scope-static-dynamic-and-runtime-augmented-5abfee6223fe)

* “**How JavaScript Works**” 是一组非常不错的文章（可能还没有写完），强烈推荐。这一系列的文章是 SessionStake 的 CEO 写的，现在有 13 篇，我感觉可能还没有写完。这个叫 [亚历山大·兹拉特科夫（Alexander Zlatkov）](https://medium.com/@zlatkov) 的 CEO 太猛了。
  * [An overview of the engine, the runtime, and the call stack](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf)
  * [Inside the V8 engine + 5 tips on how to write optimized code](https://blog.sessionstack.com/how-javascript-works-inside-the-v8-engine-5-tips-on-how-to-write-optimized-code-ac089e62b12e) ，了解 V8 引擎。这里，也推荐 [Understanding V8’s Bytecode](https://medium.com/dailyjs/understanding-v8s-bytecode-317d46c94775) 这篇文章可以让你了解 V8 引擎的底层字节码。
  * [Memory management + how to handle 4 common memory leaks](https://blog.sessionstack.com/how-javascript-works-memory-management-how-to-handle-4-common-memory-leaks-3f28b94cfbec) ，内存管理和 4 种常见的内存泄露问题。
  * [Event loop and the rise of Async programming + 5 ways to better coding with async/await](https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5) ，Event Loop 和异步编程。
  * [Deep dive into WebSockets and HTTP/2 with SSE + how to pick the right path](https://blog.sessionstack.com/how-javascript-works-deep-dive-into-websockets-and-http-2-with-sse-how-to-pick-the-right-path-584e6b8e3bf7) ，WebSocket 和 HTTP/2。
  * [A comparison with WebAssembly + why in certain cases it’s better to use it over JavaScript](https://blog.sessionstack.com/how-javascript-works-a-comparison-with-webassembly-why-in-certain-cases-its-better-to-use-it-d80945172d79) ，JavaScript 内在原理。
  * [The building blocks of Web Workers + 5 cases when you should use them](https://blog.sessionstack.com/how-javascript-works-the-building-blocks-of-web-workers-5-cases-when-you-should-use-them-a547c0757f6a) ，Web Workers 技术。
  * [Service Workers, their lifecycle and use cases](https://blog.sessionstack.com/how-javascript-works-service-workers-their-life-cycle-and-use-cases-52b19ad98b58) ，Service Worker 技术。
  * [The mechanics of Web Push Notifications](https://blog.sessionstack.com/how-javascript-works-the-mechanics-of-web-push-notifications-290176c5c55d) ，Web 端 Push 通知技术。
  * [Tracking changes in the DOM using MutationObserver](https://blog.sessionstack.com/how-javascript-works-tracking-changes-in-the-dom-using-mutationobserver-86adc7446401) ，Mutation Observer 技术。
  * [The rendering engine and tips to optimize its performance](https://blog.sessionstack.com/how-javascript-works-the-rendering-engine-and-tips-to-optimize-its-performance-7b95553baeda) ，渲染引擎和性能优化。
  * [Inside the Networking Layer + How to Optimize Its Performance and Security](https://blog.sessionstack.com/how-javascript-works-inside-the-networking-layer-how-to-optimize-its-performance-and-security-f71b7414d34c) ，网络性能和安全相关。
  * [Under the hood of CSS and JS animations + how to optimize their performance](https://blog.sessionstack.com/how-javascript-works-under-the-hood-of-css-and-js-animations-how-to-optimize-their-performance-db0e79586216) ，CSS 和 JavaScript 动画性能优化。

* 接下来是 Google Chrome 工程经理 [阿迪·奥斯马尼（Addy Osmani）](https://medium.com/@addyosmani) 的几篇 JavaScript 性能相关的文章，也是非常好的。
  * [The Cost Of JavaScript](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)
  * [JavaScript Start-up Performance](https://medium.com/reloading/javascript-start-up-performance-69200f43b201)

* 其它与 JavaScript 相关的资源。
  * [JavaScript has Unicode Problem](https://mathiasbynens.be/notes/javascript-unicode) ，这是一篇很有价值的 JavaScript 处理 Unicode 的文章。
  * [JavaScript Algorithms](https://mgechev.github.io/javascript-algorithms/index.html) ，用 JavaScript 实现的各种基础算法库。
  * [JavaScript 30 秒代码](https://github.com/30-seconds/30-seconds-of-code) ，一堆你可以在 30 秒内看懂各种有用的 JavaScript 的代码，在 GitHub 上有 2 万颗星了。
  * [What the f*ck JavaScript](https://github.com/denysdovhan/wtfjs) ，一堆 JavaScript 搞笑和比较 tricky 的样例。
  * [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) ，Airbnb 的 JavaScript 的代码规范，GitHub 上有 7 万多颗星。
  * [JavaScript Patterns for 2017](https://www.youtube.com/watch?v=hO7mzO83N1Q) ，YouTube 上的一个 JavaScript 模式分享，值得一看。

## 浏览器原理

你需要了解一下浏览器是怎么工作的，所以，你必需要看《[How browsers work](http://taligarsiel.com/Projects/howbrowserswork1.htm)》。这篇文章受众之大，后来被人重新整理并发布为《[How Browsers Work: Behind the scenes of modern web browsers](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)》，其中还包括中文版。这篇文章非常非常长，所以，你要有耐心看完。如果你想看个精简版的，可以看我在 Coolshell 上发的《[浏览器的渲染原理简介](https://coolshell.cn/articles/9666.html)》或是看一下这个[幻灯片](http://arvindr21.github.io/howBrowserWorks/#/)。

然后，是对 Virtual DOM 的学习。Virtual DOM 是 React 的一个非常核心的技术细节，它也是前端渲染和性能的关键技术。所以，你有必要要好好学习一下这个技术的实现原理和算法。当然，前提条件是你需要学习过前面我所推荐过的浏览器的工作原理。下面是一些不错的文章可以帮你学习这一技术。

* [How to write your own Virtual DOM](https://medium.com/@deathmood/how-to-write-your-own-virtual-dom-ee74acc13060)

* [Write your Virtual DOM 2: Props & Events](https://medium.com/@deathmood/write-your-virtual-dom-2-props-events-a957608f5c76)

* [How Virtual-DOM and diffing works in React](https://medium.com/@gethylgeorge/how-virtual-dom-and-diffing-works-in-react-6fc805f9f84e)

* [The Inner Workings Of Virtual DOM](https://medium.com/@rajaraodv/the-inner-workings-of-virtual-dom-666ee7ad47cf)

* [深度剖析：如何实现一个 Virtual DOM 算法](https://github.com/livoras/blog/issues/13)

* 以及两个 Vitual-DOM 实现供你参考：
  * [Matt-Esch/Virtual-DOM](https://github.com/Matt-Esch/virtual-dom)
  * [Maquette](https://maquettejs.org/)

## 网络协议

* [High Performance Browser Networking](https://book.douban.com/subject/25856314/) ，本书是谷歌公司高性能团队核心成员的权威之作，堪称实战经验与规范解读完美结合的产物。本书目标是涵盖 Web 开发者技术体系中应该掌握的所有网络及性能优化知识。全书以性能优化为主线，从 TCP、UDP 和 TLS 协议讲起，解释了如何针对这几种协议和基础设施来优化应用。然后深入探讨了无线和移动网络的工作机制。最后，揭示了 HTTP 协议的底层细节，同时详细介绍了 HTTP 2.0、 XHR、SSE、WebSocket、WebRTC 和 DataChannel 等现代浏览器新增的能力。

* 另外，[HTTP/2](https://en.wikipedia.org/wiki/HTTP/2)也是 HTTP 的一个新的协议，于 2015 年被批准通过，现在基本上所有的主流浏览器都默认启用这个协议。所以，你有必要学习一下这个协议。下面相关的学习资源。
  * [Gitbook - HTTP/2 详解](https://www.gitbook.com/?utm_source=legacy&utm_medium=redirect&utm_campaign=close_legacy)
  * [http2 explained](https://daniel.haxx.se/http2/)（[中译版](https://www.gitbook.com/?utm_source=legacy&utm_medium=redirect&utm_campaign=close_legacy)）

  * [HTTP/2 for a Faster Web](https://cascadingmedia.com/insites/2015/03/http-2.html)
  * [Nginx HTTP/2 白皮书](https://www.nginx.com/wp-content/uploads/2015/09/NGINX_HTTP2_White_Paper_v4.pdf)
  * HTTP/2 的两个 RFC：
    * [RFC 7540 - Hypertext Transfer Protocol Version 2 (HTTP/2) ](https://httpwg.org/specs/rfc7540.html)，HTTP/2 的协议本身。
    * [RFC 7541 - HPACK: Header Compression for HTTP/2](https://httpwg.org/specs/rfc7541.html) ，HTTP/2 的压缩算法。

* 新的 HTML5 支持 [WebSocket](https://en.wikipedia.org/wiki/WebSocket)，所以，这也是你要学的一个重要协议。
  * [HTML5 WebSocket: A Quantum Leap in Scalability for the Web](http://www.websocket.org/quantum.html) ，这篇文章比较了 HTTP 的几种链接方式，Polling、Long Polling 和 Streaming，并引入了终级解决方案 WebSocket。你知道的，了解一个技术的缘由是非常重要的。
  * [StackOverflow: My Understanding of HTTP Polling, Long Polling, HTTP Streaming and WebSockets](https://stackoverflow.com/questions/12555043/my-understanding-of-http-polling-long-polling-http-streaming-and-websockets) ，这是 StackOverflow 上的一个 HTTP 各种链接方式的比较，也可以让你有所认识。
  * [An introduction to Websockets](https://blog.teamtreehouse.com/an-introduction-to-websockets) ，一个 WebSocket 的简单教程。
  * [Awesome Websockets](https://github.com/facundofarias/awesome-websockets) ，GitHub 的 Awesome 资源列表。
  * 一些和 WebSocket 相关的想法，可以开阔你的思路：
    * [Introducing WebSockets: Bringing Sockets to the Web](https://www.html5rocks.com/en/tutorials/websockets/basics/)
    * [Websockets 101](https://lucumr.pocoo.org/2012/9/24/websockets-101/)
    * [Real-Time Web by Paul Banks](https://banksco.de/p/state-of-realtime-web-2016.html)
    * [Are WebSockets the future?](https://samsaffron.com/archive/2015/12/29/websockets-caution-required)

## 小结

总结一下今天的内容。我一直认为学习任何知识都要从基础出发，所以今天我主要讲述了 HTML 5、CSS 3 和 JavaScript（ES6）这三大基础核心，给出了大量的图书、文章以及其他一些相关的学习资源。之后，我建议你学习浏览器的工作原理和网络协议相关的内容。我认为，掌握这些原理也是学好前端知识的前提和基础。值得花时间，好好学习消化。

下篇文章中，我们将讲讲如何做前端性能优化，并推荐一些好用的前端框架。敬请期待。

