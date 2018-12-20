## 文件路径

`sass/_init/_mixin.scss`

## 内容

| 方法 | 参数 | 作用 | 示例
| ------ | ------ | ------ | ------ |
| unit | number | 转换当前单位，比如你想转成rem |  `font-size:unit(12);` |
| hide | null | 用clip方式隐藏元素 |  `@include hide；` |
| cell | null | 用表格的方式撑满浮动之后的剩余空间 |  `@include cell；` |
| ell | null | 单行文本点点点 |  `@include ell；` |
| ellrows | number | 多行文本点点点 |  `@include ellrows(2)；` |
| clearfix | null | 清除浮动 |  `@include clearfix；` |
| font-face | [string, string] | 创建字体| `@include font-face('fontname','../font/fontname.font')；` |
| acss-margin | Array | 创建基于 ACSS 的 4 个方向的外间距 |  `@include acss-margin((4,8,16,32))；` |
| acss-padding | Array | 创建基于 ACSS 的 4 个方向的内间距 |  `@include acss-padding((4,8,16,32))；` |
| acss-font-size | Array | 创建基于 ACSS 的多个字号 |  `@include acss-font-size((0, 12, 14, 16))；` |
| acss-line-height | Array | 创建基于 ACSS 的多个行高 |  `@include acss-line-height((16, 20, 24, 32))；` |

