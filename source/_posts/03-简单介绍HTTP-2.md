---
title: 简单介绍HTTP
date: 2019-01-22 17:13:54
tags: HTTP
---

# 简单介绍**HTTP**
这篇文章将简要的介绍一下几个部分内容
- HTTP 请求与响应包括哪些部分
- 如何用Chrome开发者工具查看 HTTP 请求与响应内容
- 如何使用 curl 命令

### HTTP 请求
客户端（Client）通过发送HTTP请求向服务器（Server）的80端口请求资源访问
#### HTTP请求最多包含四部分，最少包含三部分，他的格式是：
1. **动词 路径 协议/版本** 
   动词有 GET POST PUT PATCH DELETE HEAD OPTIONS 等
   路径以“\”开头，不写默认为“\”
   

   **动词**|**作用**
   :---|:---
   GET|向服务器获取资源
   POST|向服务器发送请求，要求服务器接收附在请求后面的数据
   PUT|整体更新
   PATCH|局部更新

2. **Key: value** ( 第二部分可以有很多组 key:value)
3.  （第三部分是一个回车，用来分隔第二与底四部分）
4. **要上传的数据**


### HTTP 响应
客户端向服务器发送请求后，服务器随之发出响应
#### 响应的格式如下
1. **协议/版本号 状态码 状态解释**
  **状态代码由三位数字组成，表示请求是否被理解或被满足，状态描述给出了关于状态代码的简短文本描述**

  1xx：指示信息——表示请求已经接受，继续处理
  2xx：成功——表示请求已经被成功接收、理解、接受。
  3xx：重定向——要完成请求必须进行更进一步的操作
  4xx：客户端错误——请求有语法错误或请求无法实现
  5xx：服务器端错误——服务器未能实现合法的请求。

  **常见状态代码、状态描述、说明：**

  200 OK      //客户端请求成功
  400 Bad Request  //客户端请求有语法错误，不能被服务器所理解
  401 Unauthorized //请求未经授权，这个状态代码必须和WWW-Authenticate报头域一起使用 
  403 Forbidden  //服务器收到请求，但是拒绝提供服务
  404 Not Found  //请求资源不存在，eg：输入了错误的URL
  500 Internal Server Error //服务器发生不可预期的错误
  503 Server Unavailable  //服务器当前不能处理客户端的请求，一段时间后可能恢复正常
2. **Key: value** ( 第二部分可以有很多组 key:value)
3. （第三部分是一个回车，用来分隔第二与底四部分）
4. **要下载的内容**


### 用Chrome开发者工具查看 HTTP 请求与响应内容
下面以 <a href="https://www.baidu.com/" target="_blank" >https://www.baidu.com/</a> 为例
- 右键检查打开开发者工具
- 在Network可以查看请求与响应的内容
- 刷新页面
- 点击www.baidu.com，在右侧就可以看到请求<a href="https://www.baidu.com/" target="_blank" >https://www.baidu.com/</a> 的请求与响应内容，如图/n
![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/005.png?raw=true "HTTP 请求与响应")
HTTP请求如图：
![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/006.png?raw=true "HTTP 请求与响应")
HTTP响应如图：
![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/007.png?raw=true "HTTP 请求与响应")

### 如何使用 curl 命令
除了使用Chrome以及其他浏览器查看HTTP请求和响应之外，我们还可以通过命令行查看HTTP请求和响应，用到的就是**curl命令**，同样以 <a href="https://www.baidu.com/" target="_blank" >https://www.baidu.com/</a> 为例
curl是一个功能强大的网络工具，它能够通过http、ftp等方式下载文件，也能够上传文件，这里只列出查看请求与响应的参数：
在命令行中输入**curl -X POST -s -v -H -- "https://www.baidu.com"**回车
其中以“>”开头的语句便是请求的内容
![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/008.png?raw=true "Curl查看请求与响应")
以“<”开头的语句便是响应的内容
![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/009.png?raw=true "Curl查看请求与响应")

-s/--slient 减少输出的信息，比如进度
-verbose 小写的v参数，用于打印更多信息，包括发送的请求信息，这在调试脚本是特别有用
-H/--header 指定请求头参数

