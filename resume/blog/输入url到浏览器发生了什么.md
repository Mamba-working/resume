﻿也没查什么资料，凭借计算机网络课上听到的写下的吧

# 一.识别URL
首先浏览器获得了这个地址，首先是传输协议吧，不过现在浏览器会自动输入了，用户没有必要一定输入http或者https了,会自动填补上。后面就是域名啦，这里就是baidu.com。好，第一步到此结束
# 二.寻找和这个域名对应的ip地址
在网络中寻找主机可不能仅仅依靠域名，域名是应用层中的东西，在网络层找到东西得用到ip地址。那么怎么寻找IP地址呢？得靠dns解析了。
计算机会先在本地的host文件中寻找域名对应的ip，像一本字典。（记得之前可以使用改hosts文件翻墙呢）
如果没有找到呢？
那电脑就会到本地的dns域名服务器寻找了，找不到的话就接着往上到根dns服务器。
![b853ac5c77a649836ca70e3899896ac9_hd.jpg](http://upload-images.jianshu.io/upload_images/7146340-fd5e95deb6f3e0a4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![774b521e4a69dc1e4608683ab1fe2005_hd.jpg](http://upload-images.jianshu.io/upload_images/7146340-ef0f4a3dfc0ba9bd.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

服务器发现后缀为.com便到com dns服务器下寻找，就可以找得到baidu了，紧接着就可以获得ip地址啦，然后发送给客户机。
# 三.发送请求
获得了ip地址意味着就可以找得到baidu的主机啦。
本地就会封装https请求，向百度服务器发起请求，要get一个html，传输文件又需要传输层帮助了。应用层通过套接字（socket）把请求发给传输层，在传输层主机通过ip找到服务器（http一般为80端口），经过三次握手，建立连接，然后服务器发来baidu.com的主页数据，之后浏览器便可以获得页面啦。
# 四.最后嘛
最后就是服务器和客户端总不能一直连接着吧，经过四次握手（似乎是这么说）断开连接！然后整个过程就该结束了。

不知道说的有什么问题欢迎纠错啊!
