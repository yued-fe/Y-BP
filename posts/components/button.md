
## 按钮组件

对于组件的开发，我们首推的是在开始写代码之前一定要和设计师**沟通**，看看他们对于我们组件的拓展是怎么思考的。以规避程序员和设计师拓展方式的不一致，然后导致的设计师一小改，程序员一大改的**成本问题**。

通常我们需要做一个按钮的时候，无非就从之前或者别人那里把代码拷贝过来，然后根据设计稿，改改颜色，字号什么之类的就可以了。

但随着项目扩张按钮形态的增加，如果我们一开始就不是全局的角度去设计组件，到后面就需要花更多的时间去思考按钮的**拓展性**。

举个例子比如我们有一个名为 `.btn` 的基础蓝色按钮。然后设计又给到了一个红色放到 `header` 区域中的下载按钮。你会如何拓展这个样式呢？ 

1. `.btn-header` ：基于位置
2. `.btn-red` ：基于颜色
3. `.btn-download` ：基于功能

以上三种是我们通常会用到的比较快速的**解决方案**。这三个方案之所以快速，是因为他们都是基于**当下**的**场景**去思考的。我们只是用代码描述了这个按钮和其它按钮的**区别**而已。

可是关键问题来了，既然不同点有这三个，我应该**选择**哪一个呢？其实我们以上三种都不推荐，但是如果非要在这三个里选择一种，我们会推荐**颜色**。

- 首先，如果我们 `footer` 里面也需要放一个红色的下载按钮，我们显然不能使用 `.btn-header` 这个名字来拓展我们的按钮，而应该使用 `.btn-footer`；
- 再者，如果我们在 `header` 里面需要添加一个红色的上传按钮，此时显然我们 `.btn-upload` 更满足我们的需求；

可是这样就达不到我们要**复用**样式的目的了。如果是基于颜色拓展的话，你依然可以使用 `.btn-red` 这个样式来表示在 `footer`中的红色下载按钮。因为我们要复用的是**样式**，而红色本身就是一种样式，自然拓展性会更好一点。再者按照我们的实际开发的经验，颜色的改动明显是远远低于我们位置和功能的。甚至有很多的项目，一旦主题色定下之后，基本上是不会改的。基于这个点推荐大家可以看一下张鑫旭老师的[基于CSS color属性的静态UI组件重构策略](https://www.zhangxinxu.com/wordpress/2016/11/development-ui-component-based-on-css-color/)的这篇文章。

当然改动概率很小，并不代表不会改变。或者说我们的设计师在已经有一个红色按钮的情况下，又设计了另一个红色的按钮，此时你会怎么命名另一个红色的按钮？难道要叫 `.btn-red2`?

### 按钮设计应该回归设计

此时就引出了另外一个问题，我们按钮的 UI 是设计师给的，所以对于按钮的拓展方式我们是需要和设计师**沟通**的。就像上面的问题，如果设计师给到了两个红色的按钮，那么可以和设计讨论是否考虑用其它的颜色替代。

既然是要沟通，就不能所有的拓展逻辑都是完全基于设计同学的思维方式来。我们得拿出我们的**方案**。好在的是在当下的环境中，已经有比较好的**最佳实践**了。这其中首推的是目前最火的也是火了很多年的前端 UI 框架 **Bootstrap**。他们对于按钮的封装，也几乎成为了**国际通用**的拓展规则。

这边基于**Bootstrap** [按钮组件](https://v4.bootcss.com/docs/4.0/components/buttons/)，结合我们实际的经验带大家看看，按钮的封装和拓展逻辑。文中的代码是为了解释原理的伪代码，实际开发会为了减少代码量，不会写得这么啰嗦。

### 按钮拓展方式

按钮基础样式设定完成之后，我们要做的就是思考按钮的拓展了。要拓展按钮，首先要先看看按钮的分类有哪些。

| 类型 | 类型细分 |
| ------ | ------ |
| 按钮主题 |`主按钮 primary`, `次按钮 secondary`, `成功按钮 success`, `危险按钮 danger`, `警告按钮 warning`|
| 按钮大小 |`比大更大 largex`, `大按钮 large`, `默认按钮 default`, `中号按钮 middle`, `小按钮 small`, `比小更小 smallx`|
| 按钮形状 |`链接按钮 link`, `幽灵按钮 ghost`, `胶囊按钮 capsule`, `块状按钮 block`|
| 按钮状态 |`禁用 disabled`, `鼠标移入 hover`, `鼠标按下 active`, `获取焦点 focus`, `加载 loading`|

基本上我们按钮主要可以分为以上四大类，而以上的几大类又可以互相的排列组合。

比如 `disabled`, `warning`, `ghost`, `large` 可以表示一个禁用状态下的警告幽灵大按钮。

#### 原生CSS

```HTML
<button type="button" disabled class="btn _warning _ghost _large">warning按钮</button>
<a href="javascript:;" class="btn _warning _disabled _ghost _large">warning按钮</a>
``` 
在 CSS [规范](https://yued-fe.github.io/YFE-BP/posts/styleguide/css) 中有提到通过是用下滑线作为前缀的命名规则。

#### React 

```JSX
<Button warning disabled ghost large>primary按钮</Button>
```
#### VUE

```Vue
<ui-button warning disabled ghost large>primary按钮</ui-button>
```
在类似 React 和 VUE 的场景中我们推荐直接使用 props ，当然组件内部的实现可以采用和原生 CSS 一样的逻辑。

看到这里有的同学可能会对于我们的拓展方式感到某些疑惑，因为从可读性来说以下的方式显然更加的优雅。

```JSX
<Button theme="warning" status="disabled" shape="ghost" size="large">primary按钮</Button>
```
对于这个问题我们内部也有一些讨论，这种写法是更加的具有可读性，而且自创的这些名称也不容易污染我们的按钮属性。但是基于以下 3 点考虑，我们最终还是选择了单属性控制的逻辑。

1. 原生对于按钮`disabled`的拓展方式是使用的 `<button type="button" disabled>button</button>`。我们更青睐沿用原生的方式，而不是自创一种我们以为更加优雅的逻辑；
2. 虽然在不熟悉这个按钮组件的情况下可读性是变差了，但是对于熟悉我们整个按钮逻辑的同学来说确实更加方便和简洁的，并且通常我们也不会同时在一个按钮上操作这么多的属性和状态。在这一点上，我们选择了方便使用方；
3. 在我们的 `shape` 的这个分类当中，我们的`block`状态其实可以和另外几个状态组合，此时一个shape字段满足不了，就需要开发新的兼容逻辑，而这自然提高了代码的复杂度；

### 按钮基础样式 「 _base.scss 」

```css
.btn {
      /* a 链接默认为inline元素，但也有可能显示为按钮所以设置 inline-block 属性 */
      display: inline-block; 
      
      /* 按钮文字居中，特别是当我们给了按钮一个固定宽度的时候 */
      text-align: center;
      
      /* 按钮文字不换行 */
      white-space: nowrap; 
      
      /* 去掉可以用鼠标选中按钮上的文字功能，没有这个属性选中的时候会出现一个比较难看的半透明框 */
      user-select: none;  
      
      /* 为非可选标签，添加鼠标手型。大多数浏览器对于 a 标签和 button 标签默认是有这个属性的，但其它标签就不一定了 */
      cursor: pointer;
      
      /* 按钮和文字混排的时候近似垂直居中 */      
      vertical-align: middle; 
      
      /* 让padding 和 border 的宽度不影响按钮大小，IE8 和 IE8 以上才兼容这个属性 */
      box-sizing: border-box;
      
      /* 按钮需要设计字体，这里为了保持统一建议和全站主字体保持一致 */
      /* 但是通常我们在 css reset 中会做这一步的重置，所以这里不需要了 */
      /* font-family:inherit; */
      
      /* 以下样式根据实际设计情况来编辑 */
     
      /* 按钮圆角 */
      border-radius: 3px; 
      
      /* 去掉按钮的默认边框 */
      border: none 0; 
}          
```
对于按钮基础样式，因为没有涉及到按钮的拓展性，所以大家的样式基本都大同小异。

### 按钮主题 「 _theme.scss 」

按钮主题其实是按照功能区分，只是设计师通常用颜色区分功能，所以主题也近似可以看作是颜色的区分。

Bootstrap 是一个没有特定产品的通用基础框架，即使在按钮设计极致收敛的情况下，仍然有 "Primary, Secondary, Success, Danger, Warning, Info, Light , Dark， Link" 九种主题（在我们看来 `link` 状态的按钮也可以表达 `primary` 的作用，所以不同于 Bootstrap 我们把 `Link` 归类到了形状这个分类中）。

对于我们自己的产品来说，这么多的分类是不推荐的。我们期望的是，用更少的主题适应更多的场景，要达到这一点，也是需要多和设计师沟通的。以我们的经验， `主按钮 primary`, `次按钮 secondary`, `成功按钮 success`, `危险按钮 danger`, `警告按钮 warning` 这5种主题已经能涵盖很大一部分场景了。

```SCSS
.btn._primary{
      color:$c_priamry;
      background-color:$c_primary;
}
```

按钮的主题色，在实际开发中我们的颜色应该是基于全局的颜色参数去获取的。对于全局颜色参数的命名，我们推荐使用 c_ 前缀。

### 按钮大小 「 _size.scss 」

`比大更大 largex`， `大按钮 large`， `默认按钮 default`， `中号按钮 middle`， `小按钮 small`，`比小更小 smallx`...

在大小的数量上和主题逻辑是一样的，建议使用更少的大小，适配更多的场景，我们推荐使用大，中，小，加默认共计四种样式。

当然如果要拓展大话，我们建议通过类似衣服尺码 xs, xl 添加 x 的方式进行拓展 _largex。

对于按钮尺寸是设定逻辑，我们建议遵从 Metiral Design 的 8 point 规则(尺寸控制在8像素的倍数，实在不能满足也应该至少是4的倍数)。

```SCSS
.btn{
	height: 40px;
	font-size: 16px;
	line-height: 24px;
	padding: 8px 16px;
}

.btn._middle{
	height: 32px;
	font-size: 14px;
	line-height: 24px;
	padding: 4px 12px;
}
```
对于大小，应该不只是按钮的高宽的变化，同时应该需要考虑到按钮字号的变化，这样才会更加的协调。

### 按钮形状 「 _shape.scss 」

`实心按钮 fill`, `链接按钮 link`, `幽灵按钮 ghost`, `胶囊按钮 capsule`, `块状按钮 block`...

按钮的形状，基本上业界常用的是以上五种方式，当然也不排除设计有定制的需求。

#### `实心按钮 fill`

<img width="82" alt="qq20181228-135519 2x" src="https://user-images.githubusercontent.com/7261176/50504697-58ad9600-0aaa-11e9-9662-cf61fd78299e.png">

```
  .btn._fill{
      color:#fff;
  }    
```

背景是主题色，文字是白色的按钮，因为太常用所以一般作为默认按钮的样式，所以在实际开发种我们不会另起一个`fill`的属性。

#### `链接按钮 link`

<img width="82" alt="qq20181228-135634 2x" src="https://user-images.githubusercontent.com/7261176/50504703-5cd9b380-0aaa-11e9-815f-8bdd18c2936d.png">

```
  .btn._link{
      background-color: transparent;
  }    
```

文字是主题色，背景为透明的按钮，虽然看起来是文本，但是它和其它按钮占据同样大小的空间。

#### `幽灵按钮 ghost`

<img width="82" alt="qq20181228-135527 2x" src="https://user-images.githubusercontent.com/7261176/50504699-5a775980-0aaa-11e9-85ba-b3ca134ba48b.png">

```
  .btn._ghost{
      background-color: transparent;
      border:1px solid;
      /* 兼容边框增加引起的文字偏移 */
      line-height: 24px - 1px ;
  } 
```

文字和边框是主题色，背景为透明的按钮。

`border`会默认使用文字的边框颜色，这里因为给按钮设定了边框，但是因为按钮高度是写死的，那么意味着，这里的文本会被往下推 1 个像素，这边需要对于不同的按钮做一个兼容。

#### `胶囊按钮 capsule`

<img width="90" alt="qq20181228-135602 2x" src="https://user-images.githubusercontent.com/7261176/50504702-5c411d00-0aaa-11e9-821d-94b81c0a4cd6.png">

```
  .btn._capsule{
    border-radius:100%;
  }    
```

左右两边是圆角的按钮。

#### `块状按钮 block`

<img width="371" alt="qq20181228-135703 2x" src="https://user-images.githubusercontent.com/7261176/50504704-5e0ae080-0aaa-11e9-8ff2-f4200243b74a.png">

```
  .btn._block{
    display:block;
    width:100%;   
    
    /* 如果没有给按钮设定 box-sizing:border-box; 属性，此处还应该去掉按钮左右间距。 */
    /* padding-left:0; */
    /* padding-right:0; */
  }    
```

占一行的按钮。

### 按钮状态 [_status.scss]

`:disabled 禁用状态`, `:hover 鼠标移入`, `:active 鼠标按下`,  `:focus 获取焦点`, `._loading 加载状态`...

按钮处于一些临界点的时候需要有一些特殊的状样式告知用户，按钮通常有以上的五个状态。

```css  
  /* 偷懒但简洁 */ 
  .btn{
    transition:200ms;
  } 
  
  /* 繁琐但性能更好 */
  .btn{
    transition:opacity 200ms, background-color 200ms, color 200ms;
  }  
```
因为按钮的状态切换，通常是从一个状态到另一个状态，为了让这个状态过度的更加自然，建议添加上 `transition`属性。

#### `:disabled 禁用状态`

<img width="173" alt="qq20181228-153338 2x" src="https://user-images.githubusercontent.com/7261176/50506934-39b50100-0ab6-11e9-978e-f26cbe6019c5.png">

```css
.btn:disabled, .btn._disabled {
  /* 用css的方式让元素不可被选中，不支持该属性的需要用 js 阻止事件提交 */
  pointer-events: none; 
   
  /* 修改鼠标手型为不允许 */
  cursor: not-allowed; 
  
  /* 修改透明度 */
  opacity: 0.5; 
}
```

按钮不可用状态，通常是某些只执行一次的操作，在操作完成之后的状态。或者是需要某些特定触发条件才能激活按钮。
禁用状态一般比正常按钮看起来要更弱一点。最简单的做法是降低透明度，这样的好处是不用给每个主题单独去设定一个禁用状态的颜色。
当然每个主题单独设定的视觉效果会更好。

并且 `button` 标签如果有 `disalbed` 属性还可以阻止表单的提交。

#### `:hover 鼠标移入`

<img width="155" alt="qq20181228-153722 2x" src="https://user-images.githubusercontent.com/7261176/50507001-84cf1400-0ab6-11e9-844a-7e2aa111b428.png">

```SCSS
/* 鼠标移入状态 */
.btn._primary:hover{
      background-color: darken($c_priamry,10%);
      color: darken($c_priamry,10%);
}
```
鼠标移入的状态和 `disabled` 的效果会有点相反，通常会让按钮变得更重一点。为了统一，我们建议使用，css 预处理器的 `darken` 函数，来让我们的主题色，加深 `10%`。

#### `:active 鼠标按下`

<img width="157" alt="qq20181228-154404 2x" src="https://user-images.githubusercontent.com/7261176/50507209-73d2d280-0ab7-11e9-98d1-459ef880fffc.png">

```SCSS
/* 鼠标移入状态 */
.btn:active{
   transform:scale(0.98);
}
```

`active` 是紧接着 `hover` 的一个状态，所以偷懒的话我们忽略这个状态，直接沿用 `hover` 的状态。但是像做得更好的 Metiarl Design 他们采用的是涟漪水波的效果。而我们这边采用了更简单的按下变小的逻辑「 感觉很像你拿手把按钮压扁了 」。这个效果可以和设计师沟通，权衡一下收益。

#### `:focus 获取焦点`

```SCSS
button{ 
  outline:none;
}
```

`focus` 也是容易被大家忽略，甚至是为了视觉效果而被舍弃。因为主流浏览器默认的 `focus` 状态一般会是一个蓝色渐变的阴影，通常来说设计师会认为不好看。于是我们经常会被要求用以上的代码去掉浏览器默认的行为。

对于这一点我们是非常不推崇的，因为`focus` 对于无障碍访问是非常重要的时候，当你的鼠标不能使用的时候，在有`focus` 的状态下，别人也知道当前焦点的位置，从而也能进行操作。偷懒的做法我们就是什么都不做，沿用浏览器的默认行为，如果设计师说不好看，那请麻烦设计师拿出好看的替代方案，而不是直接去掉。

#### `:loading 加载状态`

![Loading](https://user-images.githubusercontent.com/7261176/50508547-4f79f480-0abd-11e9-8dfd-382d30770e57.gif)

除了以上 4 个默认的浏览器按钮状态。通常情况下，在按钮按下之后等待 Ajax 请求结果的这段时间，我们会通过一个额外的 `Loading` 状态来告诉用户此时正在加载。并且在这段时间，一般不允许用户的二次操作，所以我们此时的状态建议是基于 `disabled` 的拓展。

此时采用 GIF 动图会是一个体验比较好的方案，但是因为我们有多种主题和其它的状态，我们就需要对不同状态做不同的 GIF 这难免有点繁琐。所以我们通常建议是使用CSS 动画来处理这部分的逻辑。

因为我们只能操控的伪元素，只有两个 `before`, `after` 所以在和设计师沟通的时候建议给设计师说一下我们最多可操控的对象只有两个。在我们项目里，我们采用了两个小圈的效果「 类似于大白眨眼睛的效果 」。




