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

### 目录
<link rel="stylesheet" href="http://yandex.st/highlightjs/6.2/styles/googlecode.min.css">
  
<script src="http://code.jquery.com/jquery-1.7.2.min.js"></script>
<script src="http://yandex.st/highlightjs/6.2/highlight.min.js"></script>
  
<script>hljs.initHighlightingOnLoad();</script>
<script type="text/javascript">
 $(document).ready(function(){
      $("h2,h3,h4,h5,h6").each(function(i,item){
        var tag = $(item).get(0).localName;
        $(item).attr("id","wow"+i);
        $("#category").append('<a class="new'+tag+'" href="#wow'+i+'">'+$(this).text()+'</a></br>');
        $(".newh2").css("margin-left",0);
        $(".newh3").css("margin-left",20);
        $(".newh4").css("margin-left",40);
        $(".newh5").css("margin-left",60);
        $(".newh6").css("margin-left",80);
      });
 });
</script>
<div id="category"></div>


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
	* 卸载Cocoapods: `sudo gem uninstall cocoapods`
	* 安装Cocoapods指定版本: `sudo gem install cocoapods -v 0.38.1  `
		
6. pod install与pod update卡住. 可以使用如下命令替代
	
	```
	pod install --verbose --no-repo-update
	
	pod update --verbose --no-repo-update
	
	```
7. 使用Cocoapods
   
   ```
	 touch Podfile
	
	 open -e Podfile
	
	 pod install --verbose --no-repo-update
   
   target "工程名字" do
     pod '库名', '~> 版本名'
	 end
   
   ```		


### 问题列表

* 这个网上很多种方法:(个人是移除cocoapods,重新安装的)

```
ERROR: While executing gem ... (Errno::EPERM) 
Operation not permitted - /usr/bin/pod
```

* ruby未更新:

```
ERROR:  While executing gem ... (Errno::EPERM)
Operation not permitted - /usr/bin/update_rubygems
```	

* [解决链接](http://www.jianshu.com/p/82a6d6c7b000)

```
from /usr/local/bin/pod:22:in `<main>'
```	

* gem未更新：

```
ERROR:  While executing gem ... (Errno::EPERM) 
Operation not permitted - /usr/bin/xcodeproj
```

