
## 按钮组件

对于组件，我们推荐的是和设计沟通达成一致之后，用更少的形态，适应更多的场景。


### 按钮基础样式 「 _base.scss 」

```css
.btn {
      display: inline-block; /* a 链接也有可能为 button 所以设置 inline-block 属性 */
      text-align: center; /* 按钮文字居中 */
      white-space: nowrap; /* 按钮文字不换行 */
      vertical-align: middle; /* 按钮和文字混排的时候对齐方式 */
      user-select: none; /* 去掉可以用鼠标选中按钮上的文字功能 */
      box-sizing: border-box; /* 让padding 和 border 的宽度不影响按钮高度*/
      border: none 0; /* 去掉按钮的默认边框 */
      border-radius: 3px; /* 按钮圆角 */
      cursor: pointer; /* 为非可选按钮的标签添加鼠标手型 */
}          
```

### 按钮主题 「 _theme.scss 」

对于按钮主题的命名规则，这边直接借用 BootStrap 的规则，而这也几乎是国际通用的拓展规则。

Bootstrap 是一个没有特定产品的通用基础框架，即使在按钮设计极致收敛的情况下，仍然有 "Primary | Secondary | Success | Danger | Warning | Info | Light | Dark" 八种。对于我们自己的产品来说，这么多的分类是非常不推荐的。我们推荐的是，用更少的主题适应更多的场景，要达到这一点，是需要多和设计师沟通的。

在CSS规范中有提到通过是用下滑线作为前缀的命名规则。在类似 React 和 VUE 的场景中我们推荐直接使用 props 去拓展组件 <Button primary />。相应的可以使用 CSS 的属性选择器去设定样式，以保证一致性 button[primary]{}。

按钮的主题色，在实际开发中我们的颜色应该是基于全局的颜色参数去获取的。对于颜色参数的命名，我们推荐使用 c_ 前缀。

### 按钮大小 「 _size.scss 」

对于按钮大小的拓展我们使用了四种按钮大小。拓展建议通过类似衣服尺码 xs, xl 添加 x 的方式进行拓展 _largex。
我们在大小的数量上和主题是一样的，建议使用更少的大小，适配更多的场景。


### 按钮形态 「 _shape.scss 」


### 按钮状态 [_status.scss]

在按钮主题的部分有写 hover 的样式， 可以在右侧括号内尝试自定义。
