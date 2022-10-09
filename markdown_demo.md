# markdown编写一个幻灯片快速入门版

![幻灯片演示GIF](https://pic.imgdb.cn/item/624662fa27f86abb2ad96d73.gif)

阅读前请仔细观看下列内容:

- 这些内容的基础都是在vscode或者atom上，==请下载插件Markdown Preview Enhanced==

不然这些元素都无法运行，同时你也无法正常的导出和编写

- 学习之前请确保你有HTML的基础和MarkDown的基础

- 最终导出的结果并非PPT,而且是HTML &nbsp; 如果你对导出文件有硬性要求(比如必须是PPT)请考虑其他软件或者方式编写

- 如果你发现这篇文章没有任何的动图或者图片，请等待网络将他们加载出来，或者尝试更换上网的节点

- 可以自由转载和引用,转载请标注原址

## 开始写幻灯片之前的准备

请在你md的文件首端写上这些代码

```text{.line-numbers}

---

presentation:

  width: 800

  height: 600

  theme: "blood.css"

  enableSpeakerNotes: true

---

```

如图所示，这些代码上面不能再有其他的代码或者文字,==必须放在最顶端==

![位置](https://pic.imgdb.cn/item/6245c72d27f86abb2a16b793.png)

## 创建一个页面

我们现在的PPT还没有出现，因为我们没有一个页面

输入`<!-- slide -->`就可以创建一个最初始的PPT页面

![正确的样子](https://pic.imgdb.cn/item/6245c7f727f86abb2a188e32.png)

我们现在就可以在这里输入一些标题和文字，md的数学符号也是可以的

![显示画面](https://pic.imgdb.cn/item/6245c83f27f86abb2a1928e3.png)

可以看到我们的页面已经可以正常显示了，接下来我们可以创建更多的页面

![更多页面代码](https://pic.imgdb.cn/item/6245c87627f86abb2a199c8e.png)

按下预览里面的》图标就可以切换到下一章

![教程演示](https://pic.imgdb.cn/item/6245c90127f86abb2a1abf9f.gif)

### 向下面创建更多的页面

我们一直在一个方向上存放PPT有的时候是不够的，有一些隐藏的信息我们希望可以通过其他方式展开，比如向下的PPT切换

我们只需要修改一下创建页面的命令就可以了

```text

原指令:<!-- slide -->

修改后:<!-- slide vertical=true -->

```

![垂直页面演示](https://pic.imgdb.cn/item/6245c9c327f86abb2a1c6b7d.gif)

## 修改幻灯片切换的形式

我们的幻灯片默认是平行移动，但是其实也提供了一些其他的特效来选择

```text

输入下列命令即可改变幻灯片过渡的方式

<!-- slide data-transition="zoom" -->

```

data-transition的可用属性有

|过渡名字|效果描述|

|-|-|

fade|交叉淡入淡出 -背景过渡的默认设置

slide|在背景之间滑动——幻灯片过渡的默认设置

convex|立方体以凸角滑动

concave|立方体以凹角滑动

zoom|缩放进入(从小到大，有视觉冲击)

![页面过渡](https://pic.imgdb.cn/item/6245cba927f86abb2a208c5e.gif)

## 修改幻灯片的背景图片

**在创建页面的时候我们需要带上属性data-background-image**

把下面的图片地址换成自己的图片即可,这样新的PPT就会拥有背景图

```HTML

<!-- slide data-background-image="图片地址" -->

```

![背景图](https://pic.imgdb.cn/item/6245cce227f86abb2a235f44.gif)

### 把幻灯片背景换成视频背景

**在创建页面的时候我们需要带上属性data-background-video**

把下面的图片地址换成自己的图片即可,这样新的PPT就会拥有背景视频

```HTML

// 注意，这个视频地址一定要是以mp4结尾(或者其他视频格式)，不能以域名(类似com)结尾

<!-- slide data-background-video="视频地址" -->

```

==此处我的鼠标一直没有动，后面的鼠标是官方的视频==

![视频背景GIF](https://pic.imgdb.cn/item/6245ce8c27f86abb2a27046f.gif)

## 添加动画

### fragment动画

![淡入淡出](https://pic.imgdb.cn/item/624585c327f86abb2a7fd1a4.gif)

可以看到，我们的文字现在有了动画，目前给文字添加动画只有用标签这种方法

官网上没有找到给markdown的文本添加动画的方法

==目前发现的在markdown中可以使用标签添加属性的只有列表一种==

如果想要使用文字动画就需要使用`<p>标签`或者`<div>标签`

```HTML{.line-numbers}

- 测试文本 <!-- .element: class="fragment" -->

```

![列表动画](https://pic.imgdb.cn/item/6245d1d127f86abb2a2e0a93.gif)

#### 当前可用的动画表格

|class属性值|效果|

|-|-|

|fragment fade-out|开始可见，淡出

|fragment fade-up|淡入时向上滑动

|fragment fade-down|淡入时向下滑动

|fragment fade-left|淡入时向左滑动

|fragment fade-right|淡入时向右滑动

|fragment fade-in-then-out|淡入，然后在下一步中淡出

|fragment fade-in-then-semi-out|淡入，然后在下一步淡出 50%

|fragment grow|放大

|fragment shrink|缩小

|fragment strike|横线划掉文字

|fragment highlight-red|将文字变为红色

|fragment highlight-green|将文本变为绿色

|fragment highlight-blue|将文本变为蓝色

|fragment highlight-current-red|将文本变为红色，然后在下一步返回原始文本

|fragment highlight-current-green|将文本变为绿色，然后在下一步返回原始文本

|fragment highlight-current-blue|将文本变为蓝色，然后在下一步返回原始文本

![一些动画演示GIF](https://pic.imgdb.cn/item/6246552027f86abb2ac178ad.gif)

### 自动过渡动画

需要使用自动过渡动画，首先你需要给我们的slide标签加上属性data-auto-animate

同时，**需要过渡的另一张幻灯片也需要加上**

```HTML

<!-- slide data-auto-animate -->

```

![列表的自动动画](https://pic.imgdb.cn/item/62465b7627f86abb2acb3d57.gif)

#### 给更多的元素添加动画

在markdown里面的元素，除了列表基本都不支持自动识别，目前的办法就是在周围加上

```HTML{.line-numbers}

<div data-id="识别值">内容</div>

```

这样大部分的内容都可以像图片一样自动过渡，不过效果差强人意

![自动过渡GIF](https://pic.imgdb.cn/item/62465e2527f86abb2ad07a08.gif)

### 演讲者模式

![演讲者面板](https://pic.imgdb.cn/item/62465fb927f86abb2ad34351.gif)

这个面板在演讲的时候只有你能看得到，你可以在上面切换幻灯片，计时，以及做一些笔记，**这些笔记其他人是看不到的**

在slide的标签里面输入

```HTML{.line-numbers}

<!-- slide data-notes="你需要在当前PPT记录的笔记" -->

```

代码

![演示1](https://pic.imgdb.cn/item/6246603727f86abb2ad42c7d.png)

演示的结果

![演示结果](https://pic.imgdb.cn/item/6246604527f86abb2ad449c9.png)

## 更多资料

[官方文档(英文)](https://revealjs.com/)

[在线可视化slide编辑器(英文)](https://slides.com/)

[官方github(英文)](https://github.com/hakimel/reveal.js#fragments)

[CSS社区百科全书](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-repeat)

[MPE官方markDown教程(中文)](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/)

作者：ThrustodyneMAKE
链接：https://www.jianshu.com/p/9e0ad1ba4efd
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。