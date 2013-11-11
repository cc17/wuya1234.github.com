---
layout: post
title: throttle/debounce: 为你的cpu减减压(前端性能优化)
category: blog
description: 函数节流
tags : [性能优化, js, throttle, tutorial]
---
{% include JB/setup %}


##throttle/debounce: 为你的cpu减减压(前端性能优化)


何为throttle, 何为debounce?

谷歌翻译给出的意思：throttle 掐死？？？   debounce 去抖  

好吧，按理解我们习惯翻译成 ——节流。

那么在什么场景下需要用到？

场景一：onresize,onscroll,onmousemove

场景二：input,autocomplete

如果我们什么都不做，浏览器将会频繁的调用你绑定的事件，如果电脑配置低就会感觉卡滞，也就是你的应用性能太差。

##入门级写法：——拖动就fire注册的事件

function onResize(){
    console.log('log');
};
window.addEventListener('resize',onResize,false)
