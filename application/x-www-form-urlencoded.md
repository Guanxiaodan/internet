# application/x-www-form-urlencoded
参考：http://blog.csdn.net/zllww123/article/details/77587292
这到底是个啥玩意???

#### 用form表单提交数据的时候，form标签有一个enctype的属性，这个属性指定将数据发到服务器时浏览器使用的编码类型。
enctype有三个值：

##### ① application/x-www-form-urlencoded：enctype默认为这种编码格式。

浏览器用这个编码格式将form数据转换成为一个字符串（name1=value1&name2=value2）

###### 当请求为GET时，
请求头：
```angular2html
GET/www.xxx.com?name=%22hello+world%22&**file=temp.png**&submit=submit HTTP/1.1 
```

###### 当请求为POST时：
请求头：
```angular2html
POST /www.baidu.com HTTP/1.1
```

请求体：
```angular2html
name=%22hello+world%22&file=temp.png&submit=submit
```

> 如果返回中文时出现乱码，则添加头信息的时候增加utf-8编码格式: "Content-Type","application/x-www-form-urlencoded; charset=UTF-8"

##### ② multipart/form-data：一般用于传输比较复杂的数据，转换为二进制的形式传输。比如图片，MP3，文件等。

##### ③ text/plain。纯文体的传输。空格转换为 “+” 加号，但不对特殊字符编码。
