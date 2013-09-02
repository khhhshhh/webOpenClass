Lecture 5 PHP基础
============

## 课程目的
* 掌握服务器概念
* 掌握客户端和服务端交互流程
* 了解静态页面和动态页面的区别
* 了解PHP的概念
* 初步掌握PHP的环境配置和安装
* PHP基本语法

## 知识点

1. 回顾前端后端是什么、各种技术的概念以及联系（浏览器、服务器、html，css，js，php，数据库）
2. 服务器的概念
3. 动态页面与静态页面的区别
3. 什么是PHP（PHP的概念）
3. PHP的作用（可以多举一些例子，微博？Facebook？）
4. PHP的历史
5. PHP基础：
  * 服务器环境和PHP运行的配置 
  * 基本概念和语法 
  * 变量、数据类型、运算符 
  * 控制流 
  * 函数
6. 简单的客户端和服务端编程:
  * 用表单做例子 
  * HTTP请求的概念 
  * GET、POST请求 
  * PHP如何处理请求

## 教学方法
* 讲解服务器基本概念
* 讲解B/S模式流程
* PHP这种语言在流程中所起到的作用

## 课程结构和内容

### 回顾已经学习过的知识（HTML、CSS、JS）
回顾已经学习过的知识，HTML、CSS、JS。然后比较现在大家能编写的页面（只有HTML、CSS、JS等静态资源）和一个完整的网站功能（有后台数据处理）上的区别。

* * *

### Web Server && URL
**Web Sever**

1. 世界上每一台联网的电脑都会有一个唯一的标识：IP
2. 通过IP可以唯一的确定世界上一台电脑
3. 当你在电脑上安装了一款特殊的软件以后，就可以让别人通过IP访问到你电脑上的文件或者直接运行你电脑上的程序。要注意的是，只能访问到特殊的文件夹的文件。
4. 你的电脑就变成了一台服务器了

**URL**

1. 例子：http://my.ss.sysu.edu.cn:8080/display/W2PSC 
2. 分析Protocol、host、port、path
3. 为了方便好记的原因，人们把IP地址速记成人类容易理解的语言：域名
3. DNS把域名解析成IP，找到目标主机，并且根据URL访问该主机上特定的文件

* * *
### 静态页面 VS 动态页面

**B/S模式**

1. 浏览器（Browser）渲染的时候只能理解一种返回的文件格式：HTML
2. 当一个浏览器通过URL请求一个服务器上的内容时候，返回的是HTML格式的内容，浏览器才能正确解析
3. 浏览器是无法得知该HTML是如何生成的，它只负责获取到文本并且解析


**静态页面**

1. URL指向一个服务器上的一个HTML文件，如：http://www.thinkphp.cn/info/154.html
2. 浏览器直接访问Server上的HTML文件，Server把这个文件内容直接给到浏览器，浏览器对HTML内容进行解析、显示
3. 因为HTML文件内容是不会变化的（除非你修改它），所以每次请求获得的内容都是相同的
4. 这种页面叫做静态页面。它无法保存数据，也无法处理数据，只能简单显示。


**动态页面**

1. URL指向的不是服务器的HTML文件，而是一个可以运行的程序
2. 浏览器通过该URL访问Server该程序的时候，Server会直接执行该程序
3. Server把该程序执行生成的文本返回给浏览器，假如你的文本是HTML格式的话，浏览器就能正确显示和渲染
4. 这种页面叫做动态页面。它可以根据你的输入数据生成不同的HTML文本，它的HTML文本不是文件中的，而是一个程序运行结束后的输出结果（这里可以类比C语言中的标准输出printf）

* * *

### 服务端语言
在服务端，能处理浏览器的请求并且生成HTML文档的编程语言有很多，如： PHP、Perl、Python、NodeJS、Ruby on Rails、Java、ASP，而我们今天要讲的就是PHP

* * *

### PHP简介

**What is PHP**

1. PHP Hypertext Preprocessor，递归定义。
2. 运行在服务端的脚本语言
3. 用来生成动态的Web页面的（也就是动态生成HTML页面的）


**PHP的历史**

（http://developer.51cto.com/art/200806/93892.htm）

1. PHP诞生于1994年
2. 由Rasmus Lerdorf编写创建
3. 原名为Personal Home Page Tools
4. 现已经发展到PHP 5.5

**PHP的执行过程**

（此处应该有Web Browser和Web Server交互图）

1. 浏览器如果请求服务器上的`.html`文件，服务器只会把该文件的内容直接发送到浏览器中
2. 浏览器如果请求服务器上的`.php`文件，服务器会
	1. 读取该php文件，解析其中的代码
	2. 按照php语言规则执行内部的代码
	3. 把php脚本的执行结果（通常是一个HTML文本）返回给浏览器

**Why PHP**

80.9% 的网站都采用PHP写成 （[服务端编程语言排行](http://w3techs.com/technologies/overview/programming_language/all "服务端编程语言排行")）（排行榜图表）。Why？

1. 开源，免费
2. 兼容，支持所有主流服务器
3. 简单，容易学习
 
* * *
### PHP运行环境

**环境配置**

1. [服务器安装XAMPP](http://www.apachefriends.org/zh_cn/xampp.html) 
2. XAMPP其实组合了 Windows运行平台 + Apache服务器 + MySQL数据库 + PHP运行环境
3. 为了简单起见，我们只要知道。XAMPP给我提供Web Server支持以及PHP运行环境就行了

**Hello world in PHP**

（进行实战演示）

	<?php
		echo '<h1>Hello world.</h1>';
	?>

* * *

###PHP语法基础（王青PPT）

**注释（comments）**

**输出（console）**

print 和 echo 的区别: http://www.diffen.com/difference/Echo_(PHP)_vs_Print_(PHP)

**变量**

**数据类型**

**运算操作**

**布尔类型**

**NULL**

**String类型**

**解析字符串**

**数组**

**数组操作函数**

**控制块**

（for、if/else、while）

**foreach loop**


## 扩展知识

## 开发工具
[Vim]()<br/>
[Sublime Text](http://www.sublimetext.com/)<br>
[Zend Studio](http://www.zend.com/products/studio/)<br/>
[NetBeans PHP](https://netbeans.org/features/php/)

## 推荐阅读
[PHP home page](http://www.php.net/)  
[W3Schools PHP tutorial:](http://www.w3schools.com/PHP/)  
[Practical PHP Programming:](http://hudzilla.org/phpwiki/)  
[PHP Cookbook:](http://commons.oreilly.com/wiki/index.php/PHP_Cookbook)


## 课后作业
