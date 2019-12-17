## window.length

> ## 概述
>
> 返回当前窗口中包含的框架数量(框架包括`frame`和`iframe`两种元素).
>
> ## 语法
>
> ```
> framesCount = window.length;
> ```
>
> - `framesCount`就是该窗口中框架的数量.
>
> ## 示例
>
> ```js
> if (window.length) {
>   // 该窗口包含至少一个子框架
> }
> ```
>
> ## 规范
>
> DOM Level 0 不属于任何标准.

源于修复后台web应用中(新tab标签是iframe子页面)子页面在登录失效后会跳转到登录页，于是套娃了的bug。

解决思路是利用登录页的父窗口在两种情况下不同之处做处理，找了下 window 对象的属性，发现 length 很适合，只用在登录页 login.html 加以下js即可:

```javascript
if (window.parent.length) {
		window.parent.href = 'login.html';
}
```

