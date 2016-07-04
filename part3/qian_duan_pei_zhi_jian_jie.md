## 前端配置简介

首页中定义菜单位置如下：  


![](/img/image015.jpg)
   

`index.html`中引入了`requirejs`和首页对应的初始化js文件。


![](/img/image016.jpg) 

`require.config.js`中定义了对三方技术框架的引入。  


![](/img/image017.jpg)



示例在`index.js`中初始化了菜单，用户点击对应的菜单时，路由到了对应的模块的js中，如果`pages/page.js`.  
`page.js`中指定了需要加载的模块html片段，代码如下：  
	
	define(['jquery', 'knockout', 'text!pages/goods/page.html', 'uui'], function($, ko, template)  

模块中会执行init方法，触发功能的后续步骤，如从后台获取数据，渲染界面等。在模块的js文件中，定义前端数据模型，编写前后端交互代码完成前端开发。  
此文档只简要说明代码位置及意义，具体的前端开发过程和控件使用方法，请参考官网的前端组件对应的技术文档。  