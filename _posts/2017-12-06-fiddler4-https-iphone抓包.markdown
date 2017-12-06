---
layout:     post
title:      "fiddler4-https-iphone抓包"
subtitle:   "工欲善其事，必先利其器"
date:       2017-12-06
author:     "龙龟"
header-img: "img/post-bg-fiddler4-https.jpg"
tags:
    - 移动
    - 技术
    - 工具
---

# 需要的工具 #
fiddler4 + iphone 

# 原理 #
 iphone 设置代理连接到fiddler4，通过fiddler4转发，这样就可以抓包了。https中，fiddler4其实就是中间人攻击。 fiddler4与远程服务器之间有密钥对，同时fiddler4与iphone之间也有密钥对。

# 开始 #
- 下载安装fiddler4
  
- fiddler4设置
  Tools > Options > HTTPS
  [图片](https://pan.baidu.com/s/1kVILD23)
- iphone 下载fiddler4的证书
  例如：我的pc的ip是172.18.108.249 ，那就打开safri,访问http://172.18.108.249:8888，下载证书并安装

- iphone 授权信任刚安装的证书
  iOS 10 以上的系统还需要 设置 -> 通用 -> 关于本机 -> 证书信任设置 ，信任刚才安装的证书

- 重启fiddler4，就可以抓https包了。
  但是你会看到很多Tunnel to的连接，这些是https的建立连接用的握手请求。可以忽略。设置为不显示就可以了。
  设置方法：Rules > 勾选 Hide Connects 就ok了

