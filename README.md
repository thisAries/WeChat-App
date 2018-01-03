# WeChat-App
微信小程序的使用心得

就在微信推出6.5.3版本，将小程序直接放入微信得顶部。我就知道马云的10个亿红包又白发了。

在这里我将介绍微信小程序的开发方法:

一 、 安装微信开发工具，这是下载链接：https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html 

二 、 注册微信公众号和微信小程序账号。俩个账号必须使用不同的邮箱、手机号等注册。
      随后完善小程序的信息，绑定管理员微信及开发者信息。
      
三 、 使用开发工具开发。
      这里我建议大家先下载官方提供的Demo文件，这是链接：https://mp.weixin.qq.com/debug/wxadoc/dev/demo.html
      将Demo下载好后 ，可以用开发工具打开 ，也可以在微信上预览。

四 、 开发介绍 ：

(1)
      我们可以看到根目录下有 pages 和 utils 文件夹 及 app.js、app.json、app.wxss、project.config.json;
      这些我们先不管，直接打开app.json
      
      {
        "pages":[
          "pages/index/index",
          "pages/logs/logs"
        ],
        "window":{
          "backgroundTextStyle":"light",
          "navigationBarBackgroundColor": "#fff",
          "navigationBarTitleText": "WeChat",
          "navigationBarTextStyle":"black"
        }
      }
      
      对象中"pages" 对应的是 pages文件夹, 数组中的每一项表示 "根目录pages文件夹" / "index文件夹" / "index.wxml",
      如果你在这个对象数组中直接按照格式书写 "pages/home/home" , 工具会自动在pages文件夹下生成 home 文件夹。

(2)   我们暂且称呼home 为 页面组件
      这时，你会发现所有的页面组件都是基本的套路 
              .js--逻辑
              .json--配置 
              .wxml--html 
              .wxss--css

      <1>我们先看.js

            Page({
              data: {},
              onLoad: function (options) {}
              //页面上拉触底事件的处理函数   
              onReachBottom: function (){},
              //用户点击右上角分享  
              onShareAppMessage: function () {}
            })

       基本和vue 、 react 框架的思路是一样的。

       data{name:'zdd'} ----增:直接命名 ----改:this.setData({name:'Aries'}) ----用:{{name}},属性中：class='{{name}}' => class='Aries'。
       //
       function方法是与data同级，各级之间用逗号隔开。
       写----getList(){}  or  ----getList:function(){}
       用----bindtap='getList'  ,官方提供的绑定方法是bindtap,你可以理解成点击函数onclick;值得注意的是这里的方法不能带(),也不能传值。
       方法传值只能是 "在标签内 自定义属性 data-名称='属性值' , 在js中将e或event事件给方法，调用e.target.dataset.名称"
       //
      
        

