# Quiz

## 考試題目
![alt quiz1](https://i.imgur.com/qzrDvs4.gif)

## 加分題
![alt quiz1](https://i.imgur.com/koc5JSp.gif)

![alt quiz1](https://i.imgur.com/qHPjBH3.gif)

---

## 使用技術

- vue3
- vite
- typescript
- tailwind
- scss
- pug

---

## 總結
> 遇到的問題或是困難以及學到了什麼?

### 1. width:min-content
九宮格的父元素設定完grid之後，我發現父元素的寬度比子元素寬，因為我想在父元素設置overflow:hidden，所以我必須想辦法讓父元素和子元素的寬度一致。

老實說，過去我只做過撐開子元素使其與父元素同寬的案例，這是第一次碰到反過來的情況。

還好平時就會關注新的css用法，一下就讓我想到width:min-content這個方法了！


### 2. stacking context
在格子上設置完opacity的閃爍功能後，沒想到球的隱藏跟顯示竟也一起完成了，本來以為需要另外設定的說XD 

我發現將格子設為opacity:1的時候，格子會在球的底下；將格子設為opacity:0.99的時候，反而是球會在格子底下！ 

這到底是為什麼呢?

因為添加小於1的opacity會讓元素的堆疊層級變高，導致球在格子底下

參考文章：
[什么是层叠上下文？如何形层叠上下文？层叠顺序是怎样的？](https://www.cnblogs.com/leftJS/p/11063683.html)


### 3.尚未解答的疑問

在範例二中，我在球上設置了index:20，拉高球的堆疊層級，使其不會被opacity小於1的格子覆蓋

但在範例3中，在球上設置了position: absolute後，反而讓球又重新被opacity小於1的格子覆蓋。

或許由此可知，position的層級小於opacity小於1的層級？

但如果上面結論成立的話，為什麼只有3號球會被格子覆蓋，其他的球還在格子上方呢？

我不知道這是什麼原理，還是只是視覺上的錯覺呢？

如果有高手知道答案，麻煩指教，感恩不盡！