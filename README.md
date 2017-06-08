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


