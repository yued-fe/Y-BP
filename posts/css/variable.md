## 文件路径

`sass/_init/_variable.scss`

## 简介

在开始写前端第一部分代码的时候，我们需要思考的就是参数。
参数决定着你的代码是否具有规范。

那么哪些内容可以放到我们的参数之中呢？
很简单，所有一切**值类型**的属性值，都可以放到我们的参数当中。
当然这样的属性太多了，我们肯定需要做一些甄别。
而甄别的这个过程，就是大家讨论规范的时候了。
最后**规范收敛**的内容就可以作为我们的全局基础参数了。

因为不同的团队，有着各自的规范，这边只以我们<YFE/>团队为范例。

### 基础颜色

```SCSS
$c_primary: #3b66f5; // 蓝色
$c_primary1: #6e8ffa; // 浅蓝
$c_primary2: #c2d0ff; // 比蓝更蓝
$c_danger: #f53165; // 红色
$c_danger1: #fa648c; // 浅红
$c_danger2: #ffc2d2; // 比红更红
$c_success: #39cca0; // 绿色
$c_success1: #63e0b7; // 浅绿
$c_success2: #baf5e1; // 比绿更绿
$c_warning: #ff8d29; // 黄色
$c_warning1: #ffb370; // 浅黄
$c_warning2: #ffddc2; // 比黄更黄
$c_border: #d7d8e0; // 边框颜色
$c_background: #f5f5fa; // 背景颜色
```

对于颜色，这边命名的逻辑来自 [Bootstrap](https://v4.bootcss.com/docs/4.0/components/buttons/)。
只是团队对于颜色有做收敛所以，我们颜色的类型并没有 Bootstrap 多。
如果你们团队有需要可以自己按需添加即可。

### 文字颜色

```SCSS
$c_l: #1f2129; // 文字默认颜色
$c_m: #5a5b66; // 文字辅助色
$c_s: #83848f; // 文字减弱颜色
$c_xs: #c0c2cc; // 文字比弱更弱
```

对于文字的颜色，我们采用了大家相对熟悉的衣服的尺寸来命名。
基础的逻辑是 l,m,s 三个大小，如果你想拓展就添加 x 就好。

### z-index 层级

```SCSS
$z_header: 100;   // fix 状态的 header
$z_sidebar: 110;  // 侧边栏
$z_toast: 300;   // toast提示
$z_dialog: 200;  // 弹窗
$z_overlay: 100;  // 浮层
```
统一管理 z-index 层级，解决在实际开发中为了在别的组件，z-index越来越大的问题。

### 目录其它 CSS 最佳实践

1. [CSS Variable「 参数 」](../css/variable) 
2. [CSS Mixin 「 辅助方法 」](../css/mixin)
3. [CSS Reset 「 样式重置 」](../css/reset)
4. [CSS Base 「 基础样式 」](../css/base)
5. [ACSS 「 原子化CSS 」](../css/acss)