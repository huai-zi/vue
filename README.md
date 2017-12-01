# vue
vue安装和插件的安装

##官方自带的快捷安装webpack
```
配置全局的vue-cli
$ npm install -g vue-cli
$ vue init webpack  (输入你想创建的文件夹名称)
出现以下的代码,进行配置,最后两个为no
? Project name "vue-cropper"
? Project description "A Vue.js project"
? Author "会出现你的邮件名称"
? Use ESLint to lint your code? "Yes"
? Pick an ESLint preset "Standard"
? Setup unit tests with Karma + Mocha? "No"
? Setup e2e tests with Nightwatch? "No"
配置完成,安装需要的package.json
$ cd vue-cropper
$ npm install
```

###配置完成后,会出现以下的文件夹,各自的含义
![](http://i.imgur.com/EQHLjmz.png)

###配置jQuery文件,只能在组件中使用,第三方的jQ插件不能在main.js中使用
###在使用前先使用 npm install jquery  --save 安装jQ文件
- 创建一个jquery.js文件

```
import $ from 'jQuery';
console.log($);
window.$ = $;
window.jQuery = $;
export default $
```
- 在vue组件做如下引用

```
import $ from '创建上面js文件的路径';
//调用初始化,直接使用便可
$(function(){
 $.material.init();
});
```

###加载外部的js文件

```
在webpack.config.js文件中，配置上
entry: {
		home: ['./src/main.js'],//指定打包的入口文件
		common: ['./statics/js/mui.min.js']/*定义公用的文件*/
	},这段是导包的文件，将外部的js文件进行后期的打包进入，但是在使用的过程中，还需要在使用的界面加载上此条数据
 在使用的vue页面，加载上mui.js文件，
 	var mui = require('../statics/js/mui.min.js');
  在method方法中就可以进行调用了
```

[查看文档](https://huai-zi.github.io/vue/)
