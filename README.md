## 1 需求分析

### 1.1 

## 2 分析设计图

参考资料：

* [icon](http://www.iconfont.cn)
* [在线压缩 PNG 图片](tinypng.com)
* [在线压缩 svg 图片](iconizr.com)

## 3 项目目录结构

## 4 代码分析

### 4.1 准备工作

* [在线思维导图工具：百度脑图](http://naotu.baidu.com/)
* [在线原型设计工具：墨刀](https://modao.cc/)
* [在线API文档编写工具：ShowDoc](https://www.showdoc.cc/)
* [官方接口组件文档](https://mp.weixin.qq.com/debug/wxadoc/dev/index.html?t=2017117)
* [可视化编辑器白鹭Egret Wing](https://www.egret.com/products/wing.html)
* [微信官方IDE](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html)
* [小程序界面样式库weui-wxss](https://github.com/weui/weui-wxss)
* [官方Demo代码](https://mp.weixin.qq.com/debug/wxadoc/dev/demo.html)
* [接口联调插件Postman](https://www.getpostman.com/)
* [腾讯云小程序后端开发套件wafer](https://github.com/tencentyun/wafer)
* [腾讯云wafer自行部署方案](http://www.jianshu.com/p/b381ad61b6f0)

### 4.2 前端开发

#### 4.2.1 根据所构思的产品的相关功能，采用「百度脑图」来规范化产品的功能模块。

> 去粗取精，将与产品功能相关的想法进行梳理。

产生一个产品idea后，我一般做法是尽快记录到备忘录。随后围绕这个产品的功能、市场、特色、使用流程等其它想法，不断补充到备忘录上。这样随着记录越多，产品也会变得越复杂。这时，可以采用脑图工具，借鉴一般App的设计，对备忘录上关于功能和流程的记录做重新梳理，确定整个产品的模块划分及各个模块下的小功能，剥离出相同的功能。如下图，这是早期小打卡的功能模块划分。只保留了我认为比不可少的功能，产品的第一屏我准备放置四个平级的主页面，每个主页面又包含相应的次级页面和功能。

#### 4.2.2 根据完成的“功能模块设计”，采用“墨刀”在线设计完成产品的原型图。

> 借助简单的原型设计工具，在编码之前，以较低的成本将创意可视化。

这一步，其实需要你简单了解一下现在小程序开发中可用到的UI组件，在小程序官方文档的组件这部分内容中，详细介绍了小程序提供的视图容器、表单、媒体、导航等组件，在开发之前，你至少要弄明白这些组件长啥样子，初期保证功能优先，在设计你的小程序时，先别瞎折腾华丽的界面，应该尽量参考官方已有的组件来设计你的产品，这样可以先跳过UI设计这个阶段，并且在编写前端代码的阶段，你可以复用官方提供的组件和代码，至多只需对官方组件进行稍微改动。从而可以事半功倍地进行开发。此外这些所谓的UI组件应用很广泛，在各类App上基本都能见到。在墨刀这个在线原型设计网站上，你可以拖拽式地设计你的小程序界面。

#### 4.2.3 使用“白鹭Egret Wing”和“微信官方IDE”编写前端代码

> 使用两个工具搭配，更高效地开发。

工欲善其事，必先利其器，小程序前端部分的开发，可以采用官方IDE+白鹭Egret Wing搭配，前者可是让你很方便的预览产品、手机扫码联调、上传你的小程序代码到线上部署。后者则弥补了官方IDE在编辑代码方面的不足，提供了很便捷的代码Page模板创建、代码补全以及实时编辑预览功能。

#### 4.2.4 仔细查阅“官方接口组件文档”弄懂小程序提供的相关组件和API。

> 对比小程序的能力，仔细分析你的产品，思考怎么组织小程序的组件和API去实现你的功能和页面。

熟读官方提供的接口及组件文档，这个阶段虽说只是编写界面展示的代码，但是你得先搞清楚小程序的基本骨架、配置、逻辑、视图及样式之间的联系。简单说，小程序包含一个描述整体程序的 App 和多个描述各自页面的 page。这里的 App 是指放在根目录的app.js/app.json/app.wxss这三个文件，他们主要负责全局性的逻辑、配置及样式。page则是你即将编写的多个页面，对应到你的原型设计中的每一页，多个page之间可以通过官方提供的导航功能进行跳转。每个page页面由page.js/page.json/page.wxml/page.wxss四个文件组成，其中wxml页面类似于html文件，主要负责页面的结构，不过比起html来，它更加简化了，你的布局基本上是在使用和标签以及其它官方文档上说明的其他标签，这里注意查看官方文档中的组件这部分的内容。

#### 4.2.5 结合“weui-wxss”和“官方Demo”的相关代码，来编写产品的前端界面的代码

> 这一步主要是对照你的原型设计，使用微信小程序的WXML语法，借助小程序的样式组件来把你的产品界面写出来。

搭建产品界面不得不提weui-wxss这个官方开源的样式库，他封装了很多实用的组件，比如图片上传、消息提示、日期选择、Tab选项卡等组件，你只需要复制相应的WXML和WXSS代码到你的项目中对应的文件里面即可。这也是一开始让你尽量参考微信已有组件来设计原型图的原因。这样做还有个好处，就是能让界面风格和微信尽量统一，保持一致。另外，官方Deom代码包含了官方组件和API的在小程序的中具体使用的代码，值得开发者借鉴使用。

总结：上面部分主要是小程序前端界面的开发流程，对于没有后端开发基础和经验的用户，想写一个没有和服务器进行数据交互的产品，基本上是可以实践了。别忘了页面逻辑写好，测试修复好bug再上线。对于有后端开发经验的朋友可以继续往下看，下面会聊聊关于怎么快速后端开发的内容，当然也是尽可能的结合已有的资源或代码。

### 4.3 后端开发

#### 4.3.1 根据“已完成的前端界面和逻辑”，采用“ShowDoc”在线完成API接口文档。

小程序通过逻辑page.js中设置数据的改变，带来界面相应的变化，需要和服务器端程序约定好数据交互的格式。
完成前端的界面以后，你可能写了一堆假界面，或者说是静态的界面。在微信小程序中，我们改变逻辑层的page.js文件中定义data对象下某个属性的值，则引起视图page.wxml文件中的该属性值自动变为改变后的值。简而言之，如果需要改变界面上的内容，比如不同的用户显示不同的昵称，我们只需要在page.js这样定义data对象数据：

data: {nickName: '某某'}

在page.xml中使用这个数据：

<view> {{nickName}}</view>

在通过网络请求后可以通过setData()函数来改变数据：

this.setData({nickName: '小打卡'})

执行这个函数操作后，你所看到的界面内容也随之改变。

因此，在写后端代码之前，我们可以先捋一捋各个页面或者功能需要发生变化的数据，并且该数据需要从服务器获取，我们通过撰写接口文档，让前后端遵循这个规定进行数据交互。下图是我的小打卡小程序的接口示例：

### 4.4 日志

### 4.5 测试

## 5 打包上线

参考资料：

* [实战：“小打卡”小程序从创意到上线完整开发过程解析](http://geek.csdn.net/news/detail/160206)
* [24小时从0到1开发阴阳师小程序](http://www.jianshu.com/p/89f6eb4aa3e6#)
* [Growth - 陪你成为顶尖开发者](https://github.com/phodal/growth)
* [](http://www.xcxwo.com/)
