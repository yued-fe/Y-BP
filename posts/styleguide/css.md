## 目录结构

```less
.
└── sass
    ├── _init
    │   ├── _init.scss      // 每个scss都需要引用这个文件，这个文件引用了下面两个文件
    │   ├── _mixin.scss     // 封装的一些辅助方法
    │   └── _variable.scss  // 全局用到的参数
    ├── global              // 全局样式
    │   ├── _acss.scss      // 原子化CSS
    │   ├── _reset.scss     // 样式重置
    │   ├── _base.scss      // 基础样式
    │   └── index.scss      // 这个文件引用了以上所有文件
    └── index
        └── index.scss
```

- 这边建议所有不会直接编译出的 CSS 的代码都以 " _ " 开头；
- 所有 SCSS 文件都需要引入 `_init/_init.scss` 文件；
- global 文件夹用于存放每个页面都需要用的样式文件；

## 基础代码

1. [CSS Variable「 参数 」](https://github.com/yued-fe/FE-BP/issues/1) 
2. [CSS Mixin 「 辅助方法 」](https://github.com/yued-fe/FE-BP/issues/2)
3. [CSS Reset 「 样式重置 」](https://github.com/yued-fe/FE-BP/issues/3)
4. [CSS Base 「 基础样式 」](https://github.com/yued-fe/FE-BP/issues/4)
5. [ACSS 「 原子化CSS 」](https://github.com/yued-fe/FE-BP/issues/5)

以上 5 个文件是我们对于 CSS 基础文件的拆分。

## 命名规范

| 命名 |  作用 | 示例
| ------ | ------ | ------ |
| `_`| 代表全局样式 | `.g_logo` |
| `-`| 非全局样式 | `.m-card` |
| `.g_`|  全局组件  | `.g_header` |
| `.i_` | 图标 | `.i_share` |
| `.c_` | 颜色 | `.c_primary` |
| `.j_` | 绑定 js 事件 | `.j_login` |
| `._on` | 辅助样式 | `.g_modal._on` |


以`_`开头的选择器不能直接写样式，必须有作用域的限制，例如`.g_mod._on` 表示弹窗开启的状态。但是`._on`本身是不能写任何 CSS 样式的;

[这篇文章](http://www.cnblogs.com/kaiye/archive/2011/06/13/3039046.html) 有介绍关于 "-" 和 "_" 作为分割符号的讨论。我们这边建议是遵从 W3C 推荐的方式使用 "-" 的方式去做分割，但是为了区分全局的样式和其他样式，我们这边的做法是用下划线作为全局样式的分割符号，用短横线作为其它样式的分割符号。

## 其它

对于其它 CSS 编写的逻辑，比如用空格还是用 Tab 去缩进文档，我们没有做硬性的要求。我们推荐使用插件来帮我做这部分的约定。

sublime CSS 美化插件：[CSS-Format](https://github.com/mutian/Sublime-CSS-Format)


