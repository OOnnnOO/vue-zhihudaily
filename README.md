# vue-zhihudaily

## 简介

[Demo](https://zhihudaily.lidong.me)

通过[知乎日报API](https://github.com/izzyleung/ZhihuDailyPurify/wiki/%E7%9F%A5%E4%B9%8E%E6%97%A5%E6%8A%A5-API-%E5%88%86%E6%9E%90)使用vue.js实现使用基本页面逻辑，获取数据，显示数据。

页面比较粗糙，还有修改，现在不太美观将就着看吧～～～

因为知乎图片有防盗链处理，我是将API中所有图片链接转换成http连接

>如果盗用网站是 https 的 protocol，而图片链接是 http 的话，则从 https 向 http 发起的请求会因为安全性的规定，而不带 referer，从而实现防盗链的绕过。[link](https://cnodejs.org/topic/5459da613e1f39344c5b3a39)

做完之后发现有更简单的方法

> 图片盗链问题使用以下meta标签解决 [link](https://github.com/walleeeee/daily-zhihu)

>```
><meta name="referrer" content="never">
>```

## 运行

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

## 声明

项目中内容的来自[知乎](http://www.zhihu.com),本项目所有内容及代码仅供私下学习参考, 不得作为其他用途
