# YFE「阅文前端团队」最佳实践

1. 从零开始建一个网站的前端代码，第一步应该思考什么？
2. 要写一个按钮组件，应该从哪里开始？
3. 要建立一个前端代码库，应该怎么组织自己的代码？
4. 我要实现一个图片裁剪的功能，有什么插件推荐啊？

以上问题由我们来告诉你答案？

## 代码规范

- [HTML 规范](https://yued-fe.github.io/YFE-BP/posts/styleguide/html)
- [CSS 规范](https://yued-fe.github.io/YFE-BP//posts/styleguide/css)
- [JS 规范](https://yued-fe.github.io/YFE-BP/posts/styleguide/js)

## 代码规范参考

1. [BootStrap](https://codeguide.bootcss.com/)
2. [@AlloyTeam](http://alloyteam.github.io/CodeGuide/)
3. [Airbnb JavaScript 编码规范（简体中文版）](https://github.com/yuche/javascript#table-of-contents)
4. [Isobar](http://coderlmn.github.io/code-standards/)
5. [网易](http://nec.netease.com/standard)

## CSS 布局
1. [左右布局](https://codepen.io/ziven27/pen/pYyXoB?editors=1100)
2. [列表布局](https://codepen.io/ziven27/pen/rReExa?editors=1100)
3. [Media布局](https://codepen.io/ziven27/pen/EMKzza?editors=1100) 
4. [不定高元素垂直居中](https://codepen.io/ziven27/pen/Ygqbxq?editors=1100)

## 私密小技巧
1. [ 移动端REM适配 ](https://www.zhangxinxu.com/wordpress/2016/08/vw-viewport-responsive-layout-typography/)


## 无UI依赖组件库 「 YF 」

| 功能   | 名称 |  推荐人 | 打分 | 推荐理由 |
|--------|-------------|------|:------:|------|
| 按钮 | [yf-button](https://github.com/yued-fe/yf-button)| [@ziven27](https://github.com/ziven27/) | 5 | 工程化思维的按钮组件，原生，REACT，VUE |


## 插件推荐


### Jquery

| 功能   | 名称 |  推荐人 | 打分 | 推荐理由 |
|--------|-------------|------|:------:|------|
| 打标签 | [taggingJS](https://github.com/axios/axios)| [@ziven27](https://github.com/ziven27/) | 4 | 其它的都有jquery ui的依赖 |


### React

| 功能   | 名称 |  推荐人 | 打分 | 推荐理由 |
|--------|-------------|------|:------:|------|
| 无线滚动 | [react-infinite-scroll-component](https://github.com/ankeetmaini/react-infinite-scroll-component)| [@ziven27](https://github.com/ziven27/) | 4 | 星数多 |
| 瀑布流 | [react-responsive-masonry](https://github.com/xuopled/react-responsive-masonry)| [@ziven27](https://github.com/ziven27/) | 4 | 自定义性高 |
| Ajax请求 | [axio](https://github.com/axios/axios)| [@ziven27](https://github.com/ziven27/) | 5 | 接口简单 |
| 头像裁剪 | [react-avatar-editor](https://github.com/mosch/react-avatar-editor)| [@ziven27](https://github.com/ziven27/) | 5 | 接口简单，demo详尽 |
| 区域滑块 | [react-rangeslider](https://github.com/whoisandy/react-rangeslider)| [@ziven27](https://github.com/ziven27/) | 5 | CSS 自定义性高 |
| 路由 | [@reach/router](https://reach.tech/router)| [@ziven27](https://github.com/ziven27/) | 5 | react-router原作者重新做的一个插件 |
| 移动端touch | [react-hammerjs](https://github.com/JedWatson/react-hammerjs)| [@ziven27](https://github.com/ziven27/) | 5 | 支持的事件丰富 |

## 插件diss

| 功能   | 名称 |  Diss人 | Diss理由 |
|--------|-------------|------|------|
| helmet | [react-helmet](https://github.com/nfl/react-helmet)| [@ziven27](https://github.com/ziven27/) | 有BUG，要升级到^6.0.0-beta |
