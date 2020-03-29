[TOC]

#  CSS3 的新特性

## 强大的 CSS3 选择器

### CSS3 选择器分类

1. 基本选择器
  
	通过基本选择器可以确定 HTML 树形结构中大多数的 DOM 元素节点。
  
	语法：
	
	|选择器|类型|功能描述|
	|:-|:---|:---|
  |*|通配选择器|选择文档中所有的HTML元素|
	|E|元素选择器|选择指定的类型的HTML元素|
	|#id|ID选择器|选择指定ID属性值为“id”的任意类型元素|
	|.class|类选择器|选择指定 class 属性值为“class”的任意类型的任意多个元素|
	|selector1,selectorN|群组选择器|将每一个选择器匹配的元素集合并|
  
2. 层次选择器
  
  层次选择器通过 HTML 的 DOM 元素间的层次关系获取元素，其主要的层次关系包括后代、父子、相邻兄弟和通用兄弟几种关系，通过其中某类关系可以方便快捷地选定需要的元素。
  
	语法：
  
	|选择器|类型|功能描述|
	|:-|:--|:---|
	|E F|后代选择器（包含选择器）|选择匹配的F元素，且匹配的F元素被包含在匹配的E元素内|
	|E>F|子选择器|选择匹配的F元素，且匹配的F元素是所匹配的E元素的子元素|
	|E+F|相邻兄弟选择器|选择匹配的F元素，且匹配的F元素位于匹配的E元素后面|
	|E~F|通用选择器|选择匹配的F元素，且位于匹配的E元素后的所有匹配的F元素|

3. 伪类选择器
  伪类选择器语法书写时和其他的 CSS 选择器写法有所区别，都以冒号（：）开头。
  1. 动态伪类选择器

  |选择器|类型|功能描述|
	|:-|:-|:-|
	|E:link|链接伪类选择器|选择匹配的E元素，而且匹配元素被定义了超链接并未被访问过。常用于链接锚点上|
	|E:visited|链接伪类选择器|选择匹配的E元素，而且匹配元素被定义了超链接并已被访问过。常用于链接锚点上|
	|E:active|用于行为伪类选择器|选择匹配的E元素，且匹配元素被激活。常用于锚点与按钮上|
	|E:hover|用户行为伪类选择器|选择匹配的E元素，且用户鼠标停留在元素E上|
	|E:focus|用户行为伪类选择器|选择匹配的E元素，且匹配的元素获得焦点|

  锚点伪类的设置遵守一个“爱恨原则”love/hate“，即”link-visited-hover-active“。

	2. 目标伪类选择器
  
	目标伪类选择器”:target“用来匹配文档（页面）的URL中某个标志符的目标元素。”:target“伪类选择器选取链接的目标元素，然后提供定义样式。

	注意：只有存在URL指向该匹配元素时，样式效果才会生效。

  |选择器|功能描述|
	|:-|:-|
	|E:target|选择匹配E的所有元素，且匹配元素被相关URL指向|

	3. 语言伪类

  通过匹配元素的lang属性可以为不同语言版本的网站相关元素设置不同的样式。

	4. UI 元素状态伪类选择器

  UI元素的状态一般包括：启用、禁用、选中、未选中、获得焦点、失去焦点、锁定和待机等。

	5. 结构伪类选择器

  |选择器|功能描述|
	|:-|:-|
	|E:first-child|作为父元素的第一个子元素的元素E|
	|E:last-child|作为父元素的最后一个子元素的元素E|
	|E:root|选择匹配元素E所在文档的根元素。在HTML文档中，根元素始终是html，此时该选择器与 html 类型选择器匹配的内容相同|
	|E f:nth-child(n)|选择父元素E的第n个子元素 F。其中 n 可以是整数（1、2、3）、关键字（even、odd）、可以是公式（2n+1、-n+5），而且 n 起始值为1，而不是0|
	|E F:nth-last-child(n)|选择元素E的倒数第n个子元素F。此选择器与 E F:nth-child(n)选择器计算顺序刚好相反，但使用方法都是一样的，其中 :nth-last-child(1) 始终匹配的是最后一个元素，与 :last-child 等同|
	|E:nth-of-type(n)|选择父元素内具有指定类型的第 n 个 E 元素|
	|E:nth-last-of-type(n)|选择父元素内具有指定类型的倒数第 n 个 E 元素|
	|E:first-of-type|选择父元素内具有指定类型的第一个 E 元素，与 E:nth-of-type(1)相同|
	|E:last-of-type|选择父元素内具有指定类型的自后一个 E 元素，与 E:nth-last-of-type(1)相同|
	|E:only-child|选择父元素只包含一个子元素，且该子元素匹配 E 元素|
	|E:only-of-type|选择父元素只包含一个同类型的子元素，且该子元素匹配 E 元素|
	|E:empty|选择没有子元素的元素，而且该元素也不包含任何文本节点|

  ":nth-child"选择的是某父元素的子元素，这个子元素并没有指定确切的类型，同时满足两个条件时方能有效果，其一是子元素，其二此子元素刚好处在那个位置；":nth-of-type"选择的是某父元素的子元素，而且这个子元素是指定类型。

	6. 否定伪类选择器

  |选择器|功能描述|
	|:-|:-|
	|E:not(F)|匹配所有除元素F外的E元素|

4. 伪元素和属性选择器

 - "::first-letter"：用来选择文本块的一个字母，除非在同一行中包含一些其他元素。"::first-letter"通常用于给文本元素添加排班细节，例如下沉字母或首字母。
 - "::first-line"：用来匹配元素的第一行文本，可以应用一些特殊的样式，给文本添加一些细微的区别。"::first-line"将匹配 block、inline-block、table-caption、table-cell等级别元素的第一行。
 - "::before"/"::after"：不是指存在于标记中的内容，而是可以插入额外内容的位置。
 - "::selection"：用来匹配突出显示的文本。【更改文本选中时的背景色、前景色】
   
	```css
	  ::selection {
			background: red;
			color: #fff;
		}
	```

5. 属性选择器

  |选择器|功能描述|
	|:-|:-|
	|E[attr]|选择匹配具有属性 attr 的 E 元素，其中 E 可以省略，表示选择定义了 attr 属性的任意类型元素|
	|E[attr=val]|选择匹配具有属性 attr 的 E 元素，并且 attr 的属性值为 val（其中 val 区分大小写），同样 E 元素省略时表示选择定义了 attr 属性值为 val 的任意类型元素|
	|E[attr\|=val]|选择匹配 E 元素，且 E 元素定义了属性 attr，attr 属性值是一个具有 val 或者以 val- 开始的属性值。常用于 lang 属性（例如 lang="en-us"）。例如 p[lang=en] 将匹配定义为英语的任何段落，无论是英式英语还是美式英语|
	|E[attr~=val]|选择匹配 E 元素，且 E 元素定义了属性 attr，attr 属性值具有多个空格分隔的值，其中一个值等于 val。例如，.info[title-=more| 将匹配元素具有类名 info，而且这个元素设置了一个属性 title，同事 title 属性值已包含了 "more" 的任何元素，例如 <a class="info" title="click here for more information">click me</a>|
	|E[attr*=val]|选择匹配元素 E，且 E 元素定义了属性 attr，其属性值任意位置包含了 "val"。换句话说，字符串 val 与属性值中的任意位置相匹配|
	|E[attr^=val]|选择匹配元素 E，且 E 元素定义了属性 attr，其属性值以 val 开头的任何字符串|
	|E[attr$=val]|选择匹配元素 E，且 E  元素定义了属性 attr，其属性值以 val 结尾的任何字符串。刚好与 E[attr^=val] 相反|

## CSS3边框

### CSS3边框颜色属性

  - border-width: 设置元素边框的粗细(默认值是 "medium" 大约等于3~4px)
  - border-color: 设置元素边框的颜色(默认色就是字体的颜色)
  - border-style: 设置元素边框的类型(必写)

  ```css
	border-style: solid;
  /* 一个值时，表示四条边都 solid 类型 */
	border-style: solid dotted;
	/* 两个值时，表示元素 "上下 左右" 边框类型*/
	border-style: solid dotted dashed;
	/* 三个值时，表示元素 "上 左右 下" 边框类型 */
	border-style: solid dotted dashed inset;
	/* 四个值时，表示元素 "上右下左" 边框类型 */
  ```

同理，border-color 和 border-width 具有一样的使用方法。

**border-style**

![img](https://res.weread.qq.com/wrepub/epub_622004_120)

### CSS3图片边框属性

border-image 属性的语法及参数：

```css
  border-image: none | <image> [<number> | <percentage>] {1,4} [/ <border-width>{1,4}] ?[stretch | repeat | round] {0,2}
	/* = */
	border-image: <border-image-source> || <border-image-slice> [/border-image-width] || <border-image-repeat>
```

- <image>: 设置背景图片，可以使用绝对或相对的URL地址，来指定边框的背景图片。
- <number>: number 是一个数值，用来设置边框或者边框背景图片的大小，其单位是像素（px），可以使用 1~4 个值，表示4个方位的值。
- <precentage>: percentage 也是用来设置边框或者边框背景图片的大小，跟 number 不同之处是，percentage 使用的是百分比。
- stretch、repeat、round: 这三个属性参数时用来设置边框背景图片的铺放方式，类似于 background-position，其中 stretch 会拉伸边框背景图片、repeat 是会重复边框背景图片、round 是平铺边框背景图片，其中 stretch 为默认值。

1. border-image-source
2. border-image-slice: 参数可以为数值也可以为百分比，被切割的部分不管什么排列方式都不变
3. border-image-width
4. border-iamge-repeat：[stretch | repeat | round] {1,2}

![border-image](https://res.weread.qq.com/wrepub/epub_622004_138)

### 圆角边框属性

border-radius 属性的语法及参数

```css
  border-radius: none | <length> {1,4}[/<length>{1,4}] ?
```

如果反斜杠符号"/"存在，"/"前面的值是设置元素圆角的水平方向半径，"/"后面的值是设置元素圆角的垂直方向半径；如果没有"/"，则元素圆角的水平和垂直方向的半径值相等。

应用：

圆、半圆、扇形、椭圆

### 盒子阴影属性

box-shadow 属性的语法及参数

```css
box-shadow: none | [ <length> <length> <length>?<length>? || <color> ] [ ,<length> <length> <length>? <length>? || <color> ]+
/* = */
box-shadow: none | [inset x-offset y-offset blur-radius spread-radius color],[inset x-offset y-offset blur-radius spread-radius color]
```

- none: 默认值，元素没有任何阴影效果
- inset: 阴影类型，可选值。如果不设置，其默认的投影方式是外阴影；如果取其唯一值"inset"，就是给元素设置内阴影。
- x-offset: 阴影水平偏移量，其值可以是正负值。如果取正值，则阴影在元素的右边，反之取负值，阴影在元素的左边。
- y-offset: 阴影垂直偏移量，其值可以是正负值。如果取正值，则阴影在元素的底部，反之取负值，阴影在元素的顶部。
- blur-radius: 阴影模糊半径，可选餐宿。其值只能是正值，如果取值为”0“时，表示阴影不具有模糊效果，如果取值越大，阴影的边缘就越模糊。
- spread-radius: 阴影扩展半径，可选参数。其值可以是正负值，如果取值为正值，则整个阴影都延展扩大，反之取值为负值，则整个阴影都缩小。
- color: 阴影颜色，可选参数，如果不设定任何颜色时，浏览器会取默认色，但各浏览器默认色不一样，特别是在 webkit 内核下的浏览器将无色，也就是透明，建议不要省略整个参数。

boder-image 不会影响对象阴影的任何外形；对象阴影同盒模型的层次一样，外阴影会在对象背景之上，内阴影会在边框之下，背景之上。

边框在内阴影之上，内阴影在背景图片之上，背景图片在背景色之上，背景色在外阴影之上。

## CSS3背景

### 背景的基本属性

- background-color: transparent || <color>
- background-image: none || <url>
- background-repeat: repeat || repeat-x || repeat-y || no-repeat
- background-attachment: scroll || fixed
- background-position: <percentage> || <length> || [left|center|right][,top|center|bottom]
- background-origin: 指定绘制背景图片的起点
- background-clip: 制定背景图片的显示范围
- background-size: 指定背景图片的尺寸大小
- background-break: 指定内联元素的背景图片进行平铺时的循环方式

```css
  background: [<background-color>] [,<background-image>] [,<background-repeat>] [,<background-attachment>] [,<background-position>]
```

**背景图片相同的定位方式**

![img](https://res.weread.qq.com/wrepub/epub_622004_185)

### 背景原点属性

background-origin 属性的语法及参数

```css
  background-origin: padding || border || content
	/* = */
	background-oriign: padding-box || border-box || content-box
```

 - padding-box(padding):默认值，决定 background-position 起始位置从 padding 的外边缘（border的内边缘）开始显示背景图片。
 - border-box(border): 决定 background-position 起始位置从 border 的外边缘开始显示背景图片。
 - content-box(content): 决定 background-position 起始位置从 content 的外边缘（padding的内边缘）开始显示背景图片。

 如果将 background-attachment 设置为 fixed，background-origin 将不起任何作用。

### 背景裁切属性

background-clip 属性的语法及参数

```css
  background-clip: border-box || padding-box || content-box
```

 - border-box: 默认值，元素背景图像从元素的 border 区域向外裁剪，即元素边框之外的背景图片都将被裁减掉。
 - padiing-box: 元素背景图像从 padding 区域向外裁剪，即元素 padding 区域外的背景图像将被裁剪掉。
 - content-box: 元素背景图像从 content 区域向外裁剪，即元素内容区域之外的背景图像将被裁减掉。

 **盒子模型**

 ![img](https://res.weread.qq.com/wrepub/epub_622004_192)

background-origin && background-clip

- background-origin: padding-box;
  - background-position: 0,0; 【背景图片定位起始点在元素padding外边缘的左上角处】
	- background-position: 100%, 100%; 【背景图片定位起始点在元素padding内边缘的右下角处】
- background-origin: border-box;
  - 背景图片定位起始点将相对于元素边框border外边缘进行定位，"0,0":左上角边框，"100%,100%":右下角边框。
- background-origin: content-box;
  - 背景图片定位起始点将相对于元素内容content外边缘进行定位，"0,0":左上角边框，"100%,100%":右下角边框。 
- background-clip: padding-box; 【元素的背景图片将忽略padding外边缘，此时元素的边框要是没有设置颜色，将显示为透明，即整个背景图片只会在padding 和 content 区域显示。】
- background-clip: border-box; 【元素的背景图片将忽略border外边缘，此时整个背景图片将显示在元素的边框底部。】
- background-clip: content-box; 【元素的背景图片将只显示在元素的内容（content）区域。】

### 背景尺寸属性

background-size 属性的语法及参数

```css
  background-size: auto || <length> || <percentage> || cover || contain
```

- auto: 默认值，将保持背景图片的原始高度和宽度。
- <length>: 取具体的整数值，将改变背景图片的大小。
- <percentage>: 取值为百分比，同样改变背景图片的大小，但此值是相对于元素的宽度来进行计算，并不是根据背景图片的宽度来进行计算。
- cover: 将背景图片放大，以适合铺满整个容器，会致使背景图片失真。
- contain: 保持背景图像本身的宽高比例，将背景图像缩放到宽度或高度正好适应所定义背景容器的区域。

## CSS3文本简介

**CSS字体类型**

|属性|功能描述|取值|
|:-|:-|:-|
|font-family|定义字体类型||
|font-style|定义字体样式|normal(默认值)、italic(斜体)、oblique(倾斜)|
|font-weight|定义字体粗细|normal(默认值)、bold(粗体)、bolder(特粗体)、lighter(细体)|
|font-size-adjust|定义是否强制对文本使用同一尺寸||
|font-stretch|定义是否横向拉伸变形字体||
|font-variant|定义字体大小写|normal(默认值)、small-caps(小型的大写字母字体)|

```css
  font: font-style [font-weight] font-size/line-height font-family;
```

**CSS文本类型**

|属性|功能描述|取值|
|:-|:-|:-|
|word-spacing|定义词与词之间的间距|normal(默认值)、length(设置词与词之间的距离，可以是负值)|
|letter-spacing|定义字符之间的距离|normal(默认值)、length(设置字符与字符之间的距离，可以是负值)|
|vertical-align|定义文本的垂直对齐方式|baseline(默认值)、sub(上标对齐)、super(下标对齐)、bottom(行框底端对齐)、text-bottom(行内文本底端对齐)、top(顶端对齐)、middle(居中个对齐)、百分比数字、长度|
|text-decoration|定义文本的修饰线|none(默认值)、underline(下划线)、overline(上划线)、line-through(删除线)、blink(闪烁线)|
|text-indent|定义文本首行缩进|length(长度单位)和百分比|
|text-align|定义文本水平对齐方式|left(左对齐)、center(居中对齐)、right(右对齐)、justify(两端对齐)|
|line-height|定义文本行高|none(默认值)、长度值、百分比值、数字|
|text-transform|定义文本大小写|none(默认值)、uppercase(大写)、lowercase(小写)、capitalize(首字大写)|
|text-shadow|定义文本阴影效果||
|white-space|定义文字之间和文本之间的空白符间距|normal(默认值)、nowrap(空白符合并、换行符忽略)、pre(空白符、换行符保留)、pre-wrap(保留空白符，正常进行换行)、pre-line(空白符合并、换行符保留)|
|direction|控制文本流入的方向|ltr(默认值)、rtl(文本从右到左流入)、inherit(文本流入方向由继承获得)|

### 文本阴影属性

text-shadow 属性的语法及参数

```css
  text-shadow: none | <length> none | [<shadow,>] * <shadow> 或 none | <color> [,color]*
  /* = */
	text-shadow: [颜色color] x轴位移(x-offset) y轴位移(y-offset) 模糊半径(blur-radius), * 
```

### 溢出文本属性

text-overflow 属性的语法及参数

```css
  text-overflow: clip | ellipsis
```

- clip: 不显示省略标记（...），只是简单的裁切。
- ellipsis: 文本溢出时显示省略标记（...），省略标记插入的位置是最后一个字符。

要实现文本溢出时裁切文本显示省略标记效果，还需要 `white-space: nowrap; overflow: hidden;` 并且需要定义容器的宽度。

### 文本换行

1. word-wrap 属性的语法及参数

```css
  word-wrap: normal | break-word
```

- normal: 默认值，浏览器只在半角空格或连字符的地方进行换行
- break-word: 将内容在边界内换行（不阶段英文单词换行）。

word-wrap 应用在 <pre> 和 <table> 中时，是没有任何效果。

2. word-break 属性的语法及参数

```css
  word-break: normal | break-all | keep-all
```

- normal: 默认值，根据语言自己的规则确定换行方式，中文到边界上的汉字换行，英文从整个单词换行。
- break-all: 可以强行截断英文单词，达到次内换行效果。
- keep-all: 不允许字断开。如果是中文把前后标点符号内的一个汉字短语整个换行，英文单词整个换行；如果出现某个英文字符长度超过容器边界，后面的部分将撑破容器；如果边框为固定属性，则后面部分无法显示。

3. white-space 属性的语法及参数

```css
  white-space: normal || pre || nowrap || pre-line || pre-wrap || inherit;
```

4. 文本换行技巧

 - pre标签自动换行
 - 单元格(td)自动换行
   
	 ```css
	   table {
			 table-layout: fixed;
			 width: **px;
		 }
		 table td {
			 overflow: hidden;
			 word-wrap: break-word;
		 }
	```

 - 除pre、td标签外其他标签自动换行

   ```css
	   element {
			 overflow: hidden;
			 word-wrap: break-word;
		 }
	```

 - 标签内容强制不换行
  
	 ```css
	   element {
			 white-space: nowrap;
			 word-break: keep-all;
		 }
	```

## 颜色特性

### 透明属性

1. opacity属性的语法及参数

  ```css
	  opacity: alphavalue || inherit;
	```

颜色的透明度可以分为 alpha 和 opacity 两种。opacity 是专门用来设置透明度的一个属性，取值范围从0~1，0表示完全透明，1表示不透明，只能给整个元素设置一个透明度，并且其透明度直接会继承给其后代元素；alpha 用来对元素设置透明度，针对元素的背景色、文字颜色、边框颜色等设置透明度。使用 transparent 属性值可以给元素的颜色设置完全透明，相等于 alpha 值设置为0。

## 盒模型

在CSS中主要有以下几种盒模型：inline、inline-block、block、table、absolute position、float。浏览器把每个元素看做一个盒模型，每一个盒模型是由以下几个属性组合所决定的：display、position、float、width、height、margin、padding、border等，不同类型的盒模型会产生不同的布局。

### 重置盒模型解析模式

1. W3C的标准盒模型

```css
  外盒尺寸计算（元素空间尺寸）
	element空间高度=内容高度+内距+边框+外距
	element空间宽度=内容宽度+内距+边框+外距
	内盒尺寸计算（元素大小）
	element高度=内容高度+内距+边框（height 为内容高度）
	element宽度=内容宽度+内距+边框（width 为内容宽度）
```

2. IE传统下盒模型

```css
  外盒尺寸计算（元素空间尺寸）
	element空间高度=内容高度+内距（height 包含了元素内容宽度、边框
	内距）
	element空间宽度=内容宽度+内距（width 包含了元素内容宽度、边框
	内距）
	内盒尺寸计算（元素大小）
	element高度=内容高度（height 包含了元素内容宽度、边框
	内距）
	element宽度=内容宽度（width 包含了元素内容宽度、边框
	内距）
```

### 盒模型属性

box-sizing属性的语法及参数

```css
  box-sizing: content-box | border-box | inherit;
```

- content-box: 默认值，标准盒模型
- border-box: 传统盒模型

在 Firefox 浏览器中，box-sizing 还可以设置一个 padding-box 属性值，用来指定元素的高度或宽度包括内容的宽度或高度和内距，但不包括边框宽度。

### 内容溢出属性

overflow-x和overflow-y属性的语法及参数

```css
  overflow-x: visible | hidden | scroll | auto | no-display | no-content;
	overflow-y: visible | hidden | scroll | auto | no-display | no-content;
```

  - no-display：当内容溢出容器时不显示元素，此时类似于元素添加了 display:none 声明一样。
	- no-content：当内容溢出容器时不显示内容，此时类似于元素添加了 visibility: hidden 声明一样。

### 自由缩放属性

resize 属性的语法及参数

```css
  resize: none | both | horizontal | vertical | inherit;
```

 - none: 用户不能拖动元素修改尺寸大小。
 - both: 用户可以拖动元素，同时修改元素的宽度和高度。
 - horizontal: 用户可以拖动元素，仅可以修改元素的宽度，但不能修改元素的高度。
 - vertical: 用户可以拖动元素，仅可以修改元素的高度，但不能修改元素的宽度。

### 外轮廓属性

outline 属性的语法及参数

```css
  outline: [outline-color] || [outline-style] || [outline-width] || [outline-offset] || inhert;
```

outline 不会影响文档流，也不会破坏网页布局；outline创建的外轮廓线始终是闭合的。

## 伸缩布局盒模型

### Flexbox 模型基础知识

1. 伸缩容器的属性

 - flex-direction: 伸缩流方向，指伸缩容器的主轴方向。默认值为 row。
 - flex-wrap: 伸缩换行，设置伸缩容器的伸缩项目是单行显示还是多行显示。默认值为 nowrap。
 - flex-flow: 伸缩方向与换行。

2. 伸缩项目的属性

 - 显示顺序。
 - 侧轴对齐：align-items 设置伸缩容器中包括匿名伸缩项目的所有项目的对齐方式；align-self 设置单独的伸缩项目上的对齐方式。
 - 伸缩性。

**主轴对齐方式：指定伸缩项目沿主轴对齐方式**

![img]("https://res.weread.qq.com/wrepub/epub_622004_271")

**侧轴对齐方式：指定伸缩项目沿侧轴对齐方式**

![img]("https://res.weread.qq.com/wrepub/epub_622004_272")

**伸缩项目对齐方式：指定伸缩项目在侧轴的对齐方式**

![img]("https://res.weread.qq.com/wrepub/epub_622004_273")

**单个伸缩项目对齐方式：指定单个伸缩项目在侧轴对齐方式**

![img]("https://res.weread.qq.com/wrepub/epub_622004_274")

**显示顺序：指定伸缩项目的顺序**

![img]("https://res.weread.qq.com/wrepub/epub_622004_275")

**伸缩性：指定伸缩项目如何伸缩尺寸**

![img]("https://res.weread.qq.com/wrepub/epub_622004_276")

**伸缩流：指定伸缩容器主轴的伸缩流方向**

![img]("https://res.weread.qq.com/wrepub/epub_622004_277")

**换行：指定伸缩项目是否沿着侧轴排列**

![img]("https://res.weread.qq.com/wrepub/epub_622004_278")

### Flexbox 模型的基本使用

1. 伸缩容器 display

```css
  display: flex | inline-flex;
```

CSS 的 columns 在伸缩容器上没有效果；float、clear 和 vertical-align 在伸缩项目上没有效果。

2. 伸缩流方向 flex-direction

```css
  flex-direction: row | row-reverse | column | column-reverse;
```

3. 伸缩换行 flex-wrap

```css
  flex-wrap: nowrap | wrap | wrap-reserve;
```

4. 伸缩流方向与换行 flex-flow

```css
  flex-flow: <'flex-direction'> || <'flex-wrap'>;
```

5. 主轴对齐 justify-content

```css
  justify-content: flex-start | flex-end | center | space-between | space-around;
```

space-around 表示伸缩项目平均分布在布局轴上，而且第一个伸缩项目前和最后一个伸缩项目后的空间为中间伸缩项目间距的一半。

6. 侧轴对齐 align-items 和 align-self

```css
  align-items: flex-start | flex-end | center | baseline | stretch;
```

7. 堆栈伸缩行 align-content 

```css
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
```

这个属性只有伸缩项目有多行时才生效，这种情况只有 display 的 flex-wrap 为 wrap 时，并且没有足够的空间把伸缩项目放在同一行中。也就是这个属性将对每一行起作用而不是每个伸缩项目。

8. 伸缩性 flex

```css
  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
```

flex 属性可以用来指定可伸缩长度的部件：扩展比率、收缩比率，以及伸缩基准值。

```css
  flex-grow: <number> (默认值为： 0)
	flex-shrink: <number> (默认值为： 1)
	flex-basis: <length> | auto (默认值为：auto)

	flex: none; == flex: 0 0 auto;
```

flex 属性常见值：

flex:0 auto和flex:initial与flex: 0 1 auto相同。这也就是flex的初始值。根据width/height属性决定元素的尺寸。如果项目的主轴长度属性的计算值为auto，则会根据其内容来决定元素尺寸。当伸缩容器额外的空间为正值时，伸缩项目无法伸缩，但当额外空间不足时，伸缩项目可收缩至其最小值。可以通过用伸缩项目的对齐相关的属性以及margin属性的auto值控制伸缩项目沿着主轴的对齐方式。

flex: auto与flex: 1 1 auto相同。根据width/height属性决定元素的尺寸，但是完全可以伸缩，会吸收主轴上额外的空间。如果所有伸缩项目均为flex: auto、flex: initial或flex:none，则在项目尺寸决定后，额外的正空间会被平分给是flex:auto的项目。

flex:none与flex: 0 0 auto相同。根据width/height属性决定元素的尺寸，但是完全不可伸缩。其效果与initial类似，但即使在空间不够而溢出的情况下，伸缩项目也不能收缩。

flex:<positive-number>与flex:<positive-number> 10px相同。该值使元素可伸缩，并将伸缩基准值设置为0，导致该项目会根据设置的比率占用伸缩容器的额外空间。如果一个伸缩容器里的所有项目都使用此模式，则它们的尺寸会正比于指定的伸缩比率。默认状态下，伸缩项目不会收缩至比其最小内容尺寸更小，可以设置min-width或min-height属性来改变这个默认状态。

9. 显示顺序 order

```css
  order: <number>;
```

## 多列布局

多列布局特性，可以让浏览器确定何时结束一列和开始下一列，无需任何额外的标记。即多列布局可以将内容按指定的列数排列，这种特性实现的布局效果和报纸、杂志排版非常相似。

1. 多列布局的属性

  - columns: 集成 column-width 和 column-count 两个属性，用于实现元素多列布局效果。
	- column-width: 定义每列列宽。
	- column-count: 定义分列列数。
	- column-gap: 定义列间距。
	- column-rule: 定义列边框。
	- column-span: 定义多列布局中子元素跨列效果。
	- column-fill: 控制每列的列高效果。

2. columns: <column-width> || <column-count>
3. 列宽属性 column-width: auto | <length>
  - auto: 默认值。
	- <length>: 使用固定值来设置元素列的宽度，其主要是由数值和长度单位组成，不过其值只能是正值，不能为负值。
4. 列数属性 column-count: auto | <integer>
  列数 = （容器宽度 - 间距） / 列间距
	对于列数的取值，是去余取整。
5. 间距属性 column-gap: normal | <length>
  - mormal: 默认值。主要通过浏览器默认设置时解析，一般情况下，normal值相当于1em。
	- <length>: 由浮点数字和单位标识符组成的长度值，主要用来设置列与列之间的距离，常用px、em单位的任何整数值，但其不能为负值。
6. 边框样式属性 column-rule: <column-rule-width>|<column-rule-style>|<column-rule-color>	

  多列列间距column-gap就类似于盒模型中的margin和padding属性，具有一定的空间位置，当其值过大时也会撑破列布局，浏览器会自动根据相关参数重新计算列数，直到容器无法容纳时，显示为一列为止。但多列列间距column-width和margin、padding属性不同的是，其只存在列与列之间，并与列高度相等。多列列边框column-rule就类似于盒模型中的border属性，主要用来设置列边框的宽度、列边框的样式和列边框颜色，并且column-rule不具有任何空间位置，同时在Z轴介于盒模型background和content之间，其同样具有与列一样的高度，但列边框column-rule和border不一样，border会撑破容器，而column-rule不会撑破容器，只不过其列宽宽度大于列间距宽度时，列边框会自动消失。
7. 跨列属性 column-span: none | all
  - none: 默认值，表示不跨越任何列。
	- all: 表示元素跨越所有列，并定位在列的Z轴之上。
8. 高度属性 column-fill: auto | balance
  - auto: 默认值，各列的高度随其内容的变化自动变化。
	- balance: 各列的高度将会根据内容最多的一列的高度进行统一。	

## 渐变

渐变是两种或多种颜色之间的平滑过渡。

### 线性渐变

1. Webkit引擎的现行渐变语法与属性参数

  1. Webkit引擎老式语法
	
	```css
	  -webkit-gradient(<type>, <point>, [,<radius>]? ,<point>[,<radius>]? [,<stop>]*)
	```
	
	2. Webkit引擎新式语法

	```css
	  -webkit-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>*])
	```

	3. Webkit引擎渐变属性参数
	  
		- 第一个参数 type 表示渐变类型，可以是线性渐变 linear 或者径向渐变 radial。
		- 第二个参数和第三个参数，都是一对值，分别表示渐变的起点位置和终点位置。这对值可以用坐标形式表示，也可以用关键值表示。【"left top"、"left bottom"...】
		- 第四个参数和第五个参数，分别是两个color-stop函数，该函数接受连个参数，第一个表示渐变的位置，0表示起点，0.5为中点，1为终点；第二个表示盖点的颜色。

	![img]("https://res.weread.qq.com/wrepub/epub_622004_361")	

2. Gecko引擎的线性渐变语法与属性参数

  ```css
	  -moz-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>]*)
	```

	- 第一个参数表示线性渐变的方向。【"left"、"top"、"left top"...】
	- 第二个和第三个参数分别是起点颜色和终点颜色。还可以在它们之间插入更多的参数，表示多种颜色的渐变。

	![img]("https://res.weread.qq.com/wrepub/epub_622004_362")

3. Presto引擎的线性渐变语法与属性参数

  ```css
	  -o-linear-gradient([<point>||<angle>,]?<stop>,<stop>[,<stop>]*)
	```

	- 第一个参数表示线性渐变的方向。【"left"、"top"、"left top"...】
	- 第二个和第三个参数分别是起点颜色和终点颜色。还可以在它们之间插入更多的参数，表示多种颜色的渐变。

	![img]("https://res.weread.qq.com/wrepub/epub_622004_363")

4. Trident引擎的线性渐变语法与属性参数

  ```css
	  -ms-linear-gradient([<point>||<agnle>,]?<stop>,<stop>[,<stop>]*)
	```

	- 第一个参数表示线性渐变的方向。【"left"、"top"、"left top"...】
	- 第二个和第三个参数分别是起点颜色和终点颜色。还可以在它们之间插入更多的参数，表示多种颜色的渐变。

	![img]("https://res.weread.qq.com/wrepub/epub_622004_363")

5. W3C标准线性渐变语法与属性参数

  ```css
	  linear-gradient([[<angle> | to <side-or-corner>],]?<color-stop>[,<color-stop>]+)
	```

	- 第一个参数指定渐变的方向，同时决定渐变颜色的停止位置。这个参数值可以省略，省略时取值为 to bottom。
	- 第二个参数和第三个参数，表示颜色的起始点和结束点，可以在它们之间插入更多的参数，表示多种颜色的渐变。

### 径向渐变

径向渐变是圆形或椭圆形渐变。颜色不再沿着一条直线轴变化，而是从一个起点朝所有方向混合。但相对线性渐变要比径向渐变复杂得多。

1. Webkit引擎的径向渐变语法

  旧版：

  ```css
    -webkit-gradient([<type>],[<position> || <angle>,]?[<shape> || <size>,]?<color-stop>, <color-stop>[,<color-stop>]*)
  ```

	新版：

	```css
	  -webkit-radial-gradient([<position> || <agnle>,]?[<shape> || <size>,]?<color-stop>, <color-stop>[,<color-stop>]*)
	```

2. Gecko引擎的径向渐变语法

  ```css
	  -moz-radial-gradient([<position> || <agnle>,]?[<shape> || <size>,]?<color-stop>, <color-stop>[,<color-stop>]*);
	```

3. Presto引擎的径向渐变语法
  
	```css
	  -o-radial-gradient([<position> || <agnle>,]?[<shape> || <size>,]?<color-stop>, <color-stop>[,<color-stop>]*);
	```

4. Trident引擎的径向渐变语法

  ```css
	  -ms-radial-gradient([<position> || <agnle>,]?[<shape> || <size>,]?<color-stop>, <color-stop>[,<color-stop>]*);
	```

5. 标准径向渐变语法

  ```css
	  radial-gradient([[<shape> || <size>] [at <position>]?, | at <position>,]?<color-stop>[,<color-stop>]+);
	```

6. 径向渐变的属性参数

  1. <position>
    主要用来定义径向渐变的圆心位置。用于确定元素渐变的中心位置。如果这个参数省略了，其默认值为 center。

		- <length>: 用长度值指定径向渐变圆心的横坐标或纵坐标，可以为负值。
		- <percentage>: 用百分比指定径向渐变原先的横坐标或纵坐标，可以为负值。
		- left: 设置左边为径向渐变圆心的横坐标值。
		- right: 设置右边为径向渐变圆心的横坐标值。
		- center: 设置中间为径向渐变圆心的横坐标值或纵坐标值。
		- top: 设置顶部为径向渐变圆心的纵坐标值。
		- bottom: 设置底部为径向渐变圆心的纵坐标值。

  2. <shape>
	  主要用来定义径向渐变的形状。其主要包括两个值 circle 和 ellipse。

		- circle: 如果 <size> 和 <length> 大小相等，径向渐变是一个圆形，也就是用来指定圆形的径向渐变。
		- ellipse: 如果 <size> 和 <length> 大小不相等，径向渐变是一个椭圆形，也就是用来指定椭圆形的径向渐变。

	3. <size>
	  用来确定径向渐变的结束形状大小。如果省略，其默认值为 farthest-corner。可以给其显式地设置一些关键词。

		- closest-side: 指定径向渐变的半径长度为从圆心到离离圆心最近的边。
		- closest-corner: 指定径向渐变的半径长度为从圆心到离圆心最近的角。
		- farthest-size: 指定径向渐变的半径长度为从圆心到离圆心最远的角。

		**如果 <shape> 设置为 circle 或者省略， <size> 可能显式设置为 <length>。表示用长度值指定径向渐变的横向或纵向直径长度，并根据横向和纵向的直径来确定径向渐变的形状是圆或者是椭圆，不能为负值。**

		注意，这里不能为百分比值，他们用来指定椭圆径向渐变的大小，而不是圆形渐变大小。

		**如果 <shape> 设置 ellipse 或者省略，<size> 可能显式设置为［<length>|<percentage>］。主要用来设置椭圆的大小。第一个值代表椭圆的水平半径，第二个值代表垂直半径。这两个值除了使用 <length> 定义大小之外还可以使用 <percentage> 来定义这两半径大小。使用 <percentage> 定义值是相对于径向渐变容器的尺寸，同样不能为负值。**
  
	4. <color-stop>

    径向渐变线上的停止颜色，类似于线性渐变的 <color-stop>，渐变线从中心点向右扩散。其中0%表示渐变线的起始点，100%表示渐变线的与渐变容器相交结束的位置，而且其颜色停止可以定义一个负值。


## 变形

### CSS变形属性及函数

CSS3变形中具有X/Y可用的函数：translateX()、translateY()、scaleX()、scaleY()、skewX()、skewY()。

CSS3 2D 变形函数包括：translate()、scale()、rotate()、skew()。
translate()函数接受CSS的标准度量单位；scale()函数接受一个0～1之间的十进制值；rotate()和skew()两个函数都接受一个径向的度量单位值deg。除了rotate()函数之外，每个函数都接受X轴和Y轴的参数。2D变形中还有一个矩阵matrix()函数，包括6个参数。

CSS3 3D 变形函数包括：rotateX()、rotateY()、rotate3d()、translateZ()、translate3d()、scaleZ()和scale3d()。3D变形中也包括一个矩阵matrix3d()函数，包括16个参数。

1. transform 属性

```css
  transform: none | <transform-function> [<transform-function>]*
```

可用于内联元素和块元素。其默认值为none，表示元素不进行变形。另一个属性值是一系列的 <transform-function>，表示一个或多个变形函数，以空格分开；换句话说就是同时对一个元素进行变形的多种属性操作，例如rotate、scale、translate等。以往叠加效果都是用逗号（，）隔开，但在transform中使用多个transform-function时却需要用空格隔开。

2. transform-function
  
	2D:
	
	- translate()：元素位移
	- scale()：元素缩放
	- rotate()：元素旋转
	- skew()：元素倾斜
	- matrix(): 定义矩阵变形

	3D:
	
	- translate3d(): 移动元素，用来指定一个 3D 变形移动位移变量。
	- translate()：指定 3D 位移在 Z 轴的位移量。
	- scale3D(): 缩放一个元素。
	- scaleZ()：指定 Z 轴的缩放向量。
	- rotate3d() 指定元素具有一个三维旋转的角度。
	- rotateX()、rotateY()、rotateZ()：让元素具有一个旋转角度。
	- perspective()：指定一个透视投影矩阵。
	- matrix3d()：定义矩阵变形。

3. transform-origin 属性

  transform-origin 属性用来指定元素的中心点位置。默认情况，变形的原点在元素的中心点，或者是元素X轴和Y轴的50%处。

	```css
	  transform-origin: [<percentage> | <length> | left | center | right | top | bottom] | [<percentage> | <length> | left | center | right ] | [[<precentage> | <length> | left | center | right] && [<percentage> | <length> | top | center | bottom]] <length> ?
	```

	**transform-orign 取值为关键词与百分比的对比**

	|关键词|百分比|
	|:-|:-|
	|top = top center = center top| 50% 0|
	|right = right center = center right|100% 或 (100% 50%)|
	|bottom = bottom center = center bottom|50% 100%|
	|left = left center = center left|0% 或 (0% 50%)|
	|center = center center|50% 或 (50% 50%)|
  |top left = left|0% 0%|
	|right top = top right|100% 0%|
	|bottom right = right bottom|100% 100%|
	|bottom left = left bottom|0% 100%|

	**transform-origin 取值及图示**

	![img](https://res.weread.qq.com/wrepub/epub_622004_427)

3. transform-style 属性

	```css
	  transform-style: flat | preserve-3d
	```

	- flat: 默认值，表示所有子元素在 2D  平面呈现.
	- preserve-3d: 所有子元素在 3D 空间中呈现。如果对一个元素设置了 transform-style 的值为 flat，该元素的所有子元素都将被平展到该元素的 2D 平面中进行呈现。沿着X轴或Y轴方向旋转该元素将导致位于正或负Z轴位置的子元素显示在该元素的平面上，而不是它的前面或者后面。
	如果对一个元素设置了 transform-style 的值为 preserve-3d，它表示不执行平展操作，它的所有子元素位于 3D 空间中。

	如果元素设置了 transform-style 值为 preserve-3d，就不能为了防止子元素溢出容器而设置 overflow 值为 hidden，如果设置了 overflow: hidden 同样可以迫使子元素出现在同一平面（和元素设置了 transform-style 为 flat 一样的效果。）

4. 2D 矩阵

  1. matrix() 函数的语法

	```css
		matrix(a, b, c, d, e, f)
	```

	![img](https://res.weread.qq.com/wrepub/epub_622004_463)

	![img](https://res.weread.qq.com/wrepub/epub_622004_464)

	= [v1*m11+v2*m12+v3*m13 
	   v1*m21+v2*m22+v3*m23 
		 v1*m31+v2*m32+v3*m33]

	![img](https://res.weread.qq.com/wrepub/epub_622004_465)	 

	2. matrix() 和各变形函数之间的关系

	  (1) 位移的 matrix() 矩阵

		```css
		  matrix(1, 0, 0, 1, tx, ty);/* tx, ty 分别对应 X 轴和 Y 轴的增量 */
		```

		(2) 缩放的 matrix() 矩阵

		```css
		  matrix(sx*x, 0, 0, sy*y, 0, 0);/* sx 和 sy 分别对应 X 轴和 Y 轴的缩放比率 */
		```

		(3) 旋转的 matrix() 矩阵

		```css
		  matrix(cos(a), sin(a), -sin(a), cos(a), 0, 0);/* cos(a) 和 sin(a)是指旋转度转*/
		```

		(4) 倾斜的 matrix() 矩阵

		```css
		  matrix(1, tan(ay), tan(ax), 1, 0, 0);/* tan(ax) 和 tan(ay) 是对应的倾斜角度 */
		```  

## CSS3过渡与动画交互效果

1. 过渡属性

```css
	transition: [<'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'> [, <'transition-property'> || <'transition-duration'> || <'transition-timing-function'> || <'transition-delay'>]]
	
	/* = */
	transition: <property> <duration> <animation type> <delay>
	/* 过渡属性， 过渡时间， 过渡动画函数，过渡延迟时间 */
```

  1. transition-property

	```css
	  transition-property: none | all | <single-transition-property> [',' <single-transition-property>]*
	```

	  - none: 没有指定任何样式。
	  - all: 默认值，表示指定元素所有支持 transition-property 属性的样式。
	  - <single-transition-property>: 指定样式，其等于 all 或 <IDENT>。

	  需要特别注意，用transition-property来指定过渡属性并不是所有属性都可以过渡，只有属性具有一个中点值的属性才能具备过渡效果，其对应的类型属性主要如下。颜色属性：通过红、绿、蓝和透明度组合的过渡（每个数值处理），如background-color、border-color、color和outline-color等CSS样式属性。具有长度值（length）、百分比（percentage）的属性：真实的数字，如word-spacing、width、vertical-align、top、right、bottom、left、min-width、min-height、maxwidth、max-height、line-height、height、background-position等。
	
	  integer：离散步骤（整个数字），在真实的数字空间，以及使用floor()转换为整数时发生，如outline-offset、z-index等。number真实的（浮点型）数值：如zoom、opacity、font-weight等。
	
	  变形系列属性：如rotate()、rotate3d()、scale()、scale3d()、skew()、translate()、tra-nslate3d()等。
	
	  rectangle：通过x、y、width和height（转为数值）变换，如crop属性。visibility：离散步骤，在0～1范围内。0表示隐藏，1表示完全显示，如visibility属性。
	
	  阴影：作用于color、x、y和blur属性，如text-shadow属性。
	
	  渐变（gradient）：通过每次停止时的位置和颜色进行变化。它们必须有相同的类型（放射状的或是线性的）和相同的停止数值以便执行动画，如background-image属性。
	
	  paint server(SVG)：只支持下面的情况。从gradient到gradient，以及color到color，然后工作与上面类似。
	
	  space-separated list of above：如果列表有相同的项目数值，则列表每一项按照上面的规则进行变化，否则无变化。
	
	  缩写属性：如果缩写的所有部分都可以实现动画，则会像所有单个属性的变化一样。
  
	2. transition-duration

	```css
	  transition-duration: <time> [,<time>]*
	```

	3. transition-timing-function

	```css
	  transition-timing-function: <single-transition-timing-function> [',' <single-transition-timing-function>]
	```

	- ease: 默认值，元素样式从初始状态过渡到终止状态时速度由快到慢，逐渐变慢。
	- linear: 元素样式从初始状态过渡到终止状态是恒速。
	- ease-in: 元素样式从初始状态过渡到终止状态时，速度越来越快，呈一种加速状态。这种效果称为渐显效果。
	- ease-out: 元素样式从初始状态过渡到终止状态时，速度越来越慢，呈一种减速状态。这种效果称为渐隐效果。
	- ease-in-out: 元素样式从初始状态到终止状态时，先加速再减速。这种效果称为渐显渐隐效果。
  - 三次贝塞尔曲线：cubic-bezier(P0,P1,P2,P3)
	- step()函数：step(<integer>[,[start|end]]?)
 
  4. transition-delay

	```css
	  transition-delay: <time>[,<time>]*
	```
	
	- 正整数：过了设定的时间值之后才触发
	- 负整数：从该时间点开始显示，之前的动作被截断。
	- 0：过渡立即触发，没有延迟。

	transition-duration 是过渡动画完成所需要的时间（也就是完成过渡动画总共用了多少时间）；transition-delay 是过渡动画在什么时间之后触发（也就是多少时间之后触发过渡动画）。

## CSS3动画

> 1. 通过类似 Flash 动画中的关键帧来声明一个动画；
> 2. 在 animation 属性中调用关键帧声明的动画，从而实现一个更为复杂的动画效果。

1. 动画属性

```css
  animation: [<animation-name> || <animation-duration> || <animation-timing-function> || <animation-delaty> || <animation-iteration-count> || <animation-direction> || <animation-play-state> || <animation-fill-mode>]*
```

  - animation-name: 用来指定一个关键帧动画的名字，这个动画名必须对应一个 @keyframes 规则。
	- animation-duration: 主要用来设置动画播放所需时间，一般以秒为单位。
	- animation-timing-function: 主要用来设置动画的播放方式，与 transition-timing-function 类似。
	- animation-delay: 主要用来指定动画开始时间、是延迟还是提前等，一般以秒为单位。
	- animation-iteration-count: 主要用来指定动画播放的循环次数。
	- animation-direction: 主要用来指定动画的播放方向。
	- animation-play-state: 主要用来控制动画的播放状态。
	- animation-fill-mode: 主要用力啊设置动画的时间外属性。

2. @keyframes

  ```css
		keyframes-rule: '@keyframes' IDENT '{' keyframes-blocks '}';
		keyframes-blocks: [keyframe-selectors block]*;
		keyframe-selectors: ['from' | 'to' PERCENTAGE][',' ['from' | 'to' | PERCENTAGE]]*;
		/* = */
		@keyframes IDENT {
			from {
				/* CSS 样式 */
			}
			percentage {
				/* CSS 样式 */
			}
			to {
				/* CSS 样式 */
			}
		}
		/* = */
		@keyframes IDENT {
      0% {
				/* CSS 样式 */
			}
			percentage {
				/* CSS 样式 */
			}
			100% {
				/* CSS 样式 */
			}
		}
	```

  - animation-direction
	  - normal: 默认值，动画的每次循环都是向前播放；
		- alternate: 动画播放为偶数次则向前播放，为奇数次则反方向播放。
	- animation-play-state
	  - running: 默认值
		- paused: 暂停动画播放，元素样式将回到最原始设置状态。
	- animation-fill-mode: 动画开始之前和结束之后发生的操作。
	  - none: 默认值，表示动画将按预期进行和结束，在动画完成其最后一帧时，动画会反转到初始帧处。
		- forwards:动画在结束后继续应用最后关键帧的位置。
		- backwords: 动画结束后会迅速应用动画的初始帧。
		- both：动画元素同时具有 forwards 和 backwords 效果。


## 媒体特性与 Responsive 设计

1. 媒体设备类型

  |值|设备类型|
	|:-|:-|
	|All|所有设备|
	|Braille|盲人用点字法触觉回馈设备|
	|Embossed|盲人打印机|
	|Hnadheld|便携设备|
	|Print|打印用纸或打印预览视图|
	|Projection|各种投影设备|
	|Screen|电脑显示器|
	|Speech|语音或音频合成器|
	|Tv|电视类型设备|
	|Tty|使用固定密度字母栅格的媒介，比如电传打字机和终端|

2. 媒体类型引用方法

  - link方法
	- xml方式
	- @import方式
	- @media方式

3. 媒体特性 Meida Query 使用方法

  - max-width 最大宽度: 指媒体类型小于或等于指定的宽度时，样式生效。
	- min-width 最小宽度: 指媒体类型大于或等于指定宽度时，样式生效。
	- 多个媒体特性使用，使用关键字 "and" 将多个媒体特性结合在一起。
	- Device Width: 设备屏幕的输出宽度
	- not 关键词：用来排除某种指定的媒体类型，也就是排除符合表达式的设备。not 关键词表示对后面的表达式执行取反操作。
	- only 关键词：用来指定某种特定的媒体类型，可以排除不支持媒体查询的浏览器。

4. Responsive 布局
  
	1. meta 标签

	```css
	  <meta name="viewport" content="">
	```
	content 属性值：
	 - width
	 - height
	 - initial-scale
	 - minimun-scale
	 - maximun-scale
	 - user-scalable

## WEB 字体

### @font-face

```css
@font-face {
	font-family: <FontName>;
	src: <source>[<format>][,<source>[<format>]]*;
	[font-weight: <weight>];
	[font-style: <style>];
}
```

- FontName: 指定的是自定义的字体名称。
- srouce: 指定的是自定义的字体存放路径，可以是相对路径也可以是绝对路径。
- format: 指定的是自定义的字体格式，主要用来帮助浏览器识别，其值主要有以下几种类型，如 truetype(.ttf)、opentype(.otf)、truetype-aat、embedded-opentype(.eot)、svg等。
- font-weight 和 font-style: 前者用来指定字体是否为粗体，后者主要定义字体样式。

### 使用字体图标的优势

- 适用性：一个图标字体比一系列的图像要小。一旦图标字体加载了，图标就会马上渲染出来，不需要下载任何图像。
- 可扩展性：图标字体可以用font-size属性设置大小。能够随时输出不同大小的图标。
- 灵活性：文字效果可以很容易地应用到图标上，包括颜色、阴影和翻转等效果。它们还可以在任何背景下显示。
- 兼容性：网页字体支持所有现代浏览器，包括低版本IE。



## 使用 CSS3 有什么好处

1. 减少开发与维护成本
2. 提高页面性能

### 渐进增强与优雅降级

#### 渐进增强

> 保证最核心的功能 => 任何低端的浏览器都能看到站点内容 => 逐步增加高级技术功能

渐进增强是一种开发方式，更是一种设计理念。在编写 Web 页面时，首先保证最核心的功能实现，让任何低端的浏览器都能看到站点内容，然后考虑用高级但非必要的 CSS 和 JavaScript 等增强功能，为当前和未来的浏览器提供更好额支持，给用户带来更好的体验。

#### 优雅降级

> 保证低端设备用户看到所有内容 => 使用高级技术功能为高端设备用户提供更好的体验

优雅降级：在设计的时候先考虑低端设备用户能否看到所有内容，然后在此基础之上为高端用户进行设计。不仅为高端设备用户提供一个完美的应用，也要为不同性能级别设备的用户设计不同级别的不那么完美的应用。
