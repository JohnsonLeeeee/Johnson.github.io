# 浅谈在小程序项目中的一些收获

## 关于wxml与wxss

首先是wxml，刚开始的时候认为wxml会与html有很大的不同，后来上手了以后才发现wxml在html的基础上做了一些比较小的改动，包括对新手更加友好了，即不需要程序员来定义各种规范，比如设置css、js文件位置，以及编码是否为utf-8等等。第二点是它对分割的块名做了一些修改，比如从div到view 等等。总的来说，wxml的改进使得越来越多的开发者可以更轻松的开发小程序。
至于wxss其实与css区别也不大，个人感觉在这次项目中对于主流的小程序框架有了一个大致的了解，尤其是点餐类的小程序，包括sidebar的设置以及dish的设置等等。
![sd](https://gitee.com/Johnsonleeeee/image/raw/master/menu.jpg)

后来其实也在考虑把side-bar改成横向的放在banner下面的位置，待以后慢慢的实验吧。

## 关于javascript

其实在本次的项目中并没有用到很多流行的框架，也没有调用他们的一些功能等等，比如vue & angular 等等，主要是调用一些微信小程序本身自带的一些功能，像wx.navigateTo wx.setStorage wx.showToast 等等这些前端的功能，当然也不乏wx.request这种向后端请求api这种功能。
在本次的项目中我也向我的组员学习到了很多，比如requestmenudata 这种函数，向后端请求数据。在这次以前实际上是没有做过前后端交互的，在这个过程中我发现微信小程序的自带功能其实很强大，包括直接调用wx.request功能即可完成请求数据的这一操作。
```
requestmenudata: function (category) {
    wx.request({
      url: 'v1/order/<:rid>',
      method: 'GET',
      header: {
        'type': category
      },
      success(res) {
        console.log(res.data);
        this.setdata({
          items: res
        });
      }
    })
  }
```

就像这样直接调用request功能即可。

## 关于工具

### 用例图
用例图的画图工具当然是选择UMLet 无论是哪种顺序图或者泳道图 UMLet都能很好地完成 只需要简单地拖动并修改该类型的属性即可。虚线实线的转换其实就是多了一个或两个<.

### 项目协作
我们是要求使用GitHub作为代码托管平台，但下载了Github Desktop这个软件以后才是真正做到了无缝对接。很多时候我们都是下午有人写到晚上，然后另一个接手从晚上写到凌晨，再由第三个人早晨起来继续写，只需要一个按钮 pull/push即可完成所有的操作，而且在history里面我们可以清楚地看到我collaborator 的贡献和修改

## 总结
感谢队友对我的包容，谢谢老师提供的机会。
