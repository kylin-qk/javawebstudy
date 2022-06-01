# servlet 入门

![image-20220531095555630](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531095555630.png)

![image-20220531095616971](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531095616971.png)

![image-20220531095843946](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531095843946.png)

![image-20220531095938211](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531095938211.png)

#### web 应用服务器程序

![image-20220531100103169](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531100103169.png)

#### J2EE 与Tomcat 的关系

![image-20220531100306757](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531100306757.png)

#### servlet

![image-20220531100501006](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531100501006.png)

#### Tomcat 与servlet 的关系

![image-20220531100555495](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531100555495.png)

下载的是apache-tomcat-8.5.79 于D盘根目录，注意下载的是J2EE 版本的开发环境，**下载好后需要绑定apache-tomcat-8.5.79：** 

![image-20220531111422264](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531111422264.png)



出现下图所示servers：对下面出现的Tomcat v8.5 进行双击配置：

![image-20220531135339733](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531135339733.png)

具体配置见下图：

![image-20220531135412187](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531135412187.png)

点击下图调试按钮：

![image-20220531135509488](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531135509488.png)

出现如下结果表示配置成功：

![image-20220531135543361](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531135543361.png)

配置成功后就书写一个Servlet程序，如下：

![image-20220531142958233](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531142958233.png)

然后在Web-INF目录下的web.xml书写如下程序：

![image-20220531143100264](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531143100264.png)

记得保存后再运行，否则会错误，第一次就错在这。

运行的步骤是：

![image-20220531143234333](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531143234333.png)

添加进去就好。就针对上面的程序，访问的方式是：在浏览器输入网址：http://localhost:8080/FirstServlet/hi?name=CTGU

就会出现如下图所示的页面：

![image-20220531143442512](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531143442512.png)

图解整个执行流程：

![image-20220531143829114](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531143829114.png)

## 标准JavaWeb 工程结构

![image-20220531144008514](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531144008514.png)

要是自己想要写一个页面作为首页，则在web context 文件目录下创建，不是在META-INF WEB-INF 目录下，如下图所示：

![image-20220531144721943](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531144721943.png)

## Servlet 开发步骤

![image-20220531211610877](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531211610877.png)

具体步骤参照上面的一个案例。

![image-20220531213953277](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531213953277.png)

看到如下这个文件则代表已经发布成功了：

![image-20220531214302189](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531214302189.png)

运行效果图如下：

![image-20220531215024959](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531215024959.png)

## 请求参数的发送和接收

在工程中创建一个student.html 文件，唯一需要做的一个动作就是如下：

![image-20220531224553352](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531224553352.png)

接着在浏览器中访问：

![image-20220531224623369](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531224623369.png)

提交表单元素后，

![image-20220531224724555](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531224724555.png)

上面的返回格式是通过 & 连接，是一组键值对。

### Servlet 接收请求参数

![image-20220531224909342](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531224909342.png)

示例代码提示如下：

![image-20220531225759778](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531225759778.png)

现在的输出见下图：

![image-20220531230005316](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531230005316.png)

## Get 与 Post 请求方法

![image-20220531230338980](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531230338980.png)

get显示在地址栏，而用Post 方式，则地址栏没有变化。

请求方法在下图进行定义：

![image-20220531231050736](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531231050736.png)

### Get 和 Post 的处理方式

![image-20220531232650601](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531232650601.png)

由于service 权限太大，所以对方法进行改写如下：

![image-20220531232819454](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531232819454.png)

### Get 与 Post 应用场景

![image-20220531232956773](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220531232956773.png)

## Servlet 生命周期

![image-20220601095543321](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601095543321.png)

## 使用注解简化配置

![image-20220601100331424](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601100331424.png)

相当于一个标志，![image-20220601101403097](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601101403097.png)

经过这个之后，不用在web.xml 中配置也可。

例子代码如下：

![image-20220601101942342](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601101942342.png)

测试结果如下：

![image-20220601101914245](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601101914245.png)

## 启动时加载 Servlet

![image-20220601102033678](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601102033678.png)

观察下图的工程目录和代码，发现这里没必要写映射：

![image-20220601103033652](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601103033652.png)

使用注解时需要特别注意这个 URL 的书写：

![image-20220601102729525](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220601102729525.png)

