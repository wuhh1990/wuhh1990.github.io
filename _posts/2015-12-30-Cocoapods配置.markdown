---
layout:     post
title:      "Cocoapods配置"
subtitle:  	 "Cocoapods常用命令，与常见问题，解决办法"
date:       2015-12-30 15:58:00
author:     "Liz"
header-img: "img/404-bg.jpg"
tags:
    - iOS
    - Cocoapods
---

> I have to do it. I have no choice.
> 我必须做到，我别无选择


## 目录
[TOC]

### 常用命令


1. 更新ruby
	* 查看ruby版本: `ruby -v`
	* [安装brew](http://brew.sh/)
	* 安装ruby: `brew install ruby`
	
2. 更新 gem
	* `$ sudo gem update --system`
	* 查看gem版本`gem -v`
	
3. 安装cocoapods
	* `$ sudo gem install cocoapods`
	* `$ pod setup`

4. 检测cocoapods版本
	* `$ pod --version`


5. 其他

	* 查看源：`gem source`
	* 移除源：`gem sources --remove https://ruby.taobao.org/`
	* 搜索库：`pod search AFNetworking`
	* 更换源：
	
		```
		gem sources --remove https://rubygems.org/
		gem sources -a https://ruby.taobao.org/
		gem sources -l
		```
		
6. pod install与pod update卡住. 可以使用如下命令替代
	
	```
	pod install --verbose --no-repo-update
	pod update --verbose --no-repo-update
	```
	


### 问题列表

1. 这个网上很多种方法:(个人是移除cocoapods,重新安装的)

```
	ERROR: While executing gem ... (Errno::EPERM) Operation not permitted - /usr/bin/pod
```

2.ruby未更新:

```
	ERROR:  While executing gem ... (Errno::EPERM)
   Operation not permitted - /usr/bin/update_rubygems
```	

3.[解决链接](http://www.jianshu.com/p/82a6d6c7b000)

```
	from /usr/local/bin/pod:22:in `<main>'
```	

4.gem未更新：

```
	ERROR:  While executing gem ... (Errno::EPERM)
   Operation not permitted - /usr/bin/xcodeproj
```

