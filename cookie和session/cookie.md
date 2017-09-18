#Cookie
参考文档：http://blog.csdn.net/fangaoxin/article/details/6952954/

cookie是一种会话跟踪技术，在客户端记录信息确定用户身份。

## 会话
一个用户在任何时段的所有请求操作都属于同一会话。而另一个用户的请求操作属于另一会话。

但是HTTP协议是无状态协议，传输完数据就断开连接了，所以当再次链接发送请求时，服务器就不知道这个请求是之前的谁发的，就不知道是属于会话A，还是属于会话B。

所以，引入了cookie机制，用来弥补HTTP协议的不足。

## cookie机制
   Cookie实际上是一小段的文本信息。客户端请求服务器，如果服务器需要记录该用户状态，就使用response向客户端浏览器颁发一个Cookie。客户端浏览器会把Cookie保存起来。当浏览器再请求该网站时，浏览器把请求的网址连同该Cookie一同提交给服务器。服务器检查该Cookie，以此来辨认用户状态。服务器还可以根据需要修改Cookie的内容。
    比如，微博服务器给你颁发一个cookie，百度服务器给你颁发一个cookie。。。
    
## 查看cookie
在地址栏输入**JavaScript:alert(document.cookie)**

例如，查看知乎的cookie：
![知乎的cookie](./1.jpg)

