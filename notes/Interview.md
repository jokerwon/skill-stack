### 1. 闭包

闭包是指有权访问另一个函数作用域中的变量的函数。当产生闭包时，闭包中的变量会常驻内存，所以使用时要注意内存泄漏问题。

在定时器、事件监听、ajax 请求等任务中，只要使用了回调函数，实际上就是在使用闭包。

闭包一般被用来封装私有变量，例如 IIFE 中就利用了闭包来进行封装。



### 2. 作用域

#### 词法作用域

词法作用域就是定义在词法阶段的作用域，简单来说可以指编写代码时所产生的作用域。与词法作用域对应的是动态作用域。

#### 函数作用域

函数作用域是指属于这个函数的全部变量可以在整个函数范围内（包括其内部嵌套的函数作用域）使用以及复用。在函数作用域外部无法直接访问内部的变量。

浏览器中存在一个全局作用域，指向 `window` 对象。Node 环境中的全局作用域指向的是 `global` 对象。由内层的函数作用域层层牵引到全局作用域的这个过程，产生了一条作用域链。

#### 块级作用域

在 ES6 之前，大概只有 `with` 和` try...catch...` 的 `catch`分支中存在块级作用域。ES6 新增了 `let`  和 `const` 关键字，从而方便地实现了块级作用域。

在有 `let` 或 `const` 声明的块级作用域中，会产生一个暂时性死区，就是说由 `let` 声明的变量，在声明之前都是无法使用的，这意味着 `let` 和 `const` 不存在变量提升，由其声明的变量也无法重复声明。



### 3. 原型