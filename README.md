# MyukiDanMu

> 原生js开发的一个简单的弹幕插件

⛄️：较为美观、占用资源较低的弹幕插件，可以设置弹幕背景，给弹幕设置内容、颜色、头像、链接地址等属性。

## 用法

0. 引入js和css文件

```javascript
<link rel="stylesheet" href="./css/MyukiDanMu.css" />
<script type="text/javascript" src="./js/MyukiDanMu.js"></script>
```

1. 创建一个MyukiDanMu实例

```javascript
//可以直接创建一个简单的实例：let obj = $MDM();
//可以直接给window绑定一个MyukiDanMu实例
window.danmuObj = $MDM({
  locate:'.AwesomeDanMu', //定位元素，需要事先设置宽高
  color:'#48dbfb', /**默认字体和鼠标悬浮时的阴影颜色
  默认值：#48dbfb
  */
  curtain:'url(./img/curtain.jpg)', /**
  弹幕墙的背景，可以是图片，也可以是颜色，比如
  - 颜色：#57606f
  - 图片：url(./img/curtain.jpg)
  默认值：#57606f
  */
  speed: 8, /**弹幕从左移动到右的时长，
  单位：s（秒）,
  默认值：8
  因为所有弹幕的运动时间相等，所以弹幕越长，速度越快
  */
  avatar: './img/avatar.jpg',/**默认弹幕的头像，
  如果不设置将不显示头像
  */
  pool:[],/**
  弹幕池，可以在创建完MyukiDanMu实例后再提供
  */
  maxPoolDelay: 5, /**两条弹幕时间间隔的最大值
  单位：s，
  默认值：5
  */
  minPoolDelay: 1,/**两条弹幕时间间隔的最小值
  单位：s，
  默认值：1
  */
  maxDanMuWidth: 250, /**
  弹幕的最大长度，
  单位：px
  如果不提供，将使用弹幕墙宽度的两倍作为弹幕最大长度
  */
});
```

2. 使用MyukiDanMu实例发送一条弹幕

```javascript
//简单用法
danmuObj.shot("我是一条弹幕");
// 高级用法
danmuObj.shot({
	danmu: '我是一条弹幕',/**
	弹幕内容
	*/
  color: '#48dbfb',/**
  弹幕颜色，可选，不提供将使用创建实例时设置的color
  */
  id: 'xxx',/**
  弹幕id，可选
  */
  url: '/#xxx',/**
  弹幕链接地址，可选
  */
  avatar: './img/avatar.jpg',/**
  弹幕头像，可选
  */
});
```

3. 使用弹幕实例发送弹幕池

```javascript
let pool = [
  {
    danmu: '我是一条弹幕',
    color: '#1e90ff',
    href: '#111',
    avatar: './img/avatar1.jpg'
  },
  {
    danmu: '我是另一条弹幕',
    color: '#1e90ff',
    href: '#222',
    avatar: './img/avatar1.jpg'
  },
  {
    danmu: '我还是一条弹幕',
    color: '#1e90ff',
    href: '#333',
    avatar: './img/avatar1.jpg'
  },
]
danmuObj.shotPool(pool);
```

## 预览

[点击访问](https://stackblog.cf/message/)

```
https://stackblog.cf/message/
```

