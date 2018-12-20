原子组件库是一种极简，高效容易管理的组件库。

是目前唯一可以做到 CSS 代码随着项目推进越来越少的代码库。

类似张老师的 [quicklayout.css](https://www.zhangxinxu.com/wordpress/2014/03/quicklayout-css-%E5%BF%AB%E9%80%9F%E6%9E%84%E5%BB%BA%E7%BB%93%E6%9E%84%E5%85%BC%E5%AE%B9%E7%9A%84web%E9%A1%B5%E9%9D%A2/ "quicklayout.css")。但是命名这边有做进一步的约束：

1. 只取首字母 `.db{ display:block; }`;
2. 有数字直接连接 `.mb10{ margin-bottom:unit(10); }`;
3. 百分号用p（percent）表示 `.w100p{ width:100%; }`;
4. 小数点用d（dot）表示  `.lh1d2{ line-height:1.2}`;


## 使用方式

### 原生 HTML 中的使用

```HTML
<div class="pl16 pr16 pt16 pb16 tac c_000">
	hello world!
</div>
```
### CSS Module 中的使用
```jsx
<div className={`pl16 pr16 pt16 pb16 tac c_000`}>
	hello world!
</div>
```
### style component 中的使用

```jsx
<div pl16 pr16 pt16 pb16 tac c_000>
	hello world!
</div>
```
表示，`padding:16p 16px 16px 16px; text-align:center; color:#000;`

## 推荐阅读

1.  [「CSS思维」组件化VS原子化 ]( https://juejin.im/post/5b4063936fb9a04fb016b738 )
2.  [ 如何管理 CSS “内裤” ]( https://juejin.im/post/5ba862d9f265da0ae472868a )
3. [quickLayout.css-快速构建结构兼容的web页面](https://link.juejin.im/?target=https%3A%2F%2Fwww.zhangxinxu.com%2Fwordpress%2F2014%2F03%2Fquicklayout-css-%25E5%25BF%25AB%25E9%2580%259F%25E6%259E%2584%25E5%25BB%25BA%25E7%25BB%2593%25E6%259E%2584%25E5%2585%25BC%25E5%25AE%25B9%25E7%259A%2584web%25E9%25A1%25B5%25E9%259D%25A2%2F)  @张老师
4.「英」[在组件化浪潮中重新思考CSS](https://link.juejin.im/?target=http%3A%2F%2Fjohnpolacek.com%2Frethinking%2F)  @johnpolacek  虽然是英文，但是网页做得像PPT一样，通俗易懂，强推；
5. [ACSS 官网](https://link.juejin.im/?target=https%3A%2F%2Facss.io%2F) @雅虎   这个思维最早应该是雅虎推出来的，最近他们有在推 React ACSS
6. [关于HTML语义和前端架构](https://link.juejin.im/?target=http%3A%2F%2Fwww.w3cplus.com%2Fcss%2Fabout-html-semantics-front-end-architecture.html) @大漠；
7. [「译」CSS通用类和“关注点分离”](https://link.juejin.im/?target=https%3A%2F%2Fwww.zcfy.cc%2Farticle%2Fcss-utility-classes-and-quote-separation-of-concerns-quote-4149.html%3Ft%3Dnew) @adamwathan；
8. [「英」Styling React](https://link.juejin.im/?target=https%3A%2F%2Fsurvivejs.com%2Freact%2Fadvanced-techniques%2Fstyling-react%2F) @SURVIVEJS；
9. [「英」CSS最佳实践探讨](https://link.juejin.im/?target=https%3A%2F%2Fwww.smashingmagazine.com%2F2013%2F10%2Fchallenging-css-best-practices-atomic-approach%2F) - Atomic CSS @smashingmagazine；
