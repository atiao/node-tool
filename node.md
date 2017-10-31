title: 基于node做一个本地的全局工具
speaker: xin
url: https://github.com/atiao/node-tool
theme: dark

[slide]
	## 打字效果
	----
	<iframe data-src="https://codepen.io/xinliqun/full/KywVqm" src="about:blank;"></iframe>
	https://codepen.io/xinliqun/pen/KywVqm
[slide]
	* 思路：
	* 让容器的宽度成为动画的主体，让文本的宽度从0开始以**步进动画**的方式，一个字一个字的扩张到它应有的宽度。
	* 但是这个方法有局限性：不适用于多行文本。
[slide]
	* 关键属性：
	* `setps()` -- 逐帧动画

	`steps()`是`animation-timing-function`性的值，这个属性规定了动画的运动曲线，常见的有`linear，ease，ease-in`等。	 
[slide]
	* `steps(n,[ start | end ] ])`，阶梯函数，可以把动画平均分成基本相等的n份。但是这个要跟`linear`区分开，`linear`之类的过渡函数会在每个关键帧之间插入补间动画，所以动画是连贯性的，而`steps`则是关键帧之间的跳跃。
[slide style="text-align:left"]
	*
	* `ch` -- 单位，表示0字形的宽度(在等宽字体中，"0"的宽度和其他字形的宽度一样。)

	* 等宽字体有：Consolas, Monaco, monospace
[slide]
	## 图片对比控件
	----
	<iframe data-src="https://codepen.io/xinliqun/full/gXOqoX" src="about:blank;"></iframe>
	https://codepen.io/xinliqun/pen/gXOqoX
[slide]
	* 关键属性：
	* resize(由用户控制div元素的大小)

	resize: none|both|horizontal|vertical;

[slide]
	用node做个全局的小工具
[slide]
	*
	* 建一个项目文件里需要package.json来管理本地安装的npm包。

	在一个空文件夹里，npm init

	注意下 index.js 入口，后续在这里面搞事情。

[slide]
	`#!/usr/bin/env node` 算是unix/linux 的写法，意思就是指定node为脚本解释语言.

[slide]
	因为我们做的是一个本地全局使用的工具，所以需要在package.json中配置bin字段，他是一个命令名和本地文件名的映射。
[slide]
	npm link 安装本地模块，并将本地模块cli化

	git地址：https://github.com/atiao/node-tool