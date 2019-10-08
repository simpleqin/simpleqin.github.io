---
layout:     post
title:      "github的markdow各种问题（公式渲染、目录等）"
date:       2019-10-08
author:     "simple"
header-img: "img/post-bg-2015.jpg"
tags:
    - markdown
---

>本篇为对github markdown中一些疑难杂症的解决。



目录

<!-- TOC -->

 [公式渲染](#公式渲染)  
 [自动生成目录](#自动生成目录)  
 [换行问题](#换行问题)  
 [待补充](#待补充)  

<!-- /TOC -->

##  公式渲染
前两天兴高采烈的写完一篇博客，上传完之后发现，嗯？我的公式怎么都这个样子了（没有渲染出来），转头一查，发现github不给渲染，那只能自己想方法了。看了几种方法之后，发现在网页中嵌入JS是最佳方案，利用MathJax帮助渲染。具体方法：  
如果你是jekyll的模板，那么你只需要在default.html的head中插入以下script即可

```
<!-- 数学公式 -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
    }
  });
</script>
```

有的default.html的头部是单独写的，你需要自己找到head.html的位置  
我第一开始从网上找了一个script发现没有效果，最后看到MathJax官网说以前的网址已弃用，而且建议使用带具体版本的链接  
MathJax官网 https://www.mathjax.org/cdn-shutting-down/

##  自动生成目录
总所周知，github的markdown是没有直接生成目录的功能的。这里给大家推荐一个非常好用的markdown编辑器--visual studio code，mac和windows都支持。如果你有这个编辑器的话，你可以在搜索栏里搜索markdown toc插件（作者Hunter tran），右键然后点击自动生成toc即可。

## 换行问题
github flavor markdown你用回车他是不会自动换行的  
解决方法：在行末加两空格即可


## 待补充
