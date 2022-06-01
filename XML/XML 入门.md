

[TOC]

# XML 入门

### 1，概念与用途

XML 的全称是 EXtensible  Markup Language ，可扩展标记语言，编写 XML 就是编写标签，与 HTML 非常相似，扩展名为 **.xml** ，它具有非常好的人机可读性。

XML 和 HTML 之间做一个比较：

- 都是编写标签的
- XML 没有预定义标签，HTML 存在大量预定义标签。什么是没有预定义的标签呢？比如说，在HTML 中段落用标签 **"<p> 段落</p>"** 标题用**“<h>标题</h>”** ，而在XML 中没有这些限制。你可以根据自己想表达的意思自定义标签。比如想表示员工（employee），就用 **<employee>员工信息</employee>** ，这看起来是不是非常直白呢?*也不是说标签没有书写规则哦，它也是有一些规则的。* 
- XML 重在保存与传输数据，HTML 用于显示信息

XML 用途：

- Java 程序的配置描述文件
- 用于保存程序产生的数据
- 网络间数据传输

### 2，XML 文档结构

XML 声明说明XML 文档的基本信息，包括版本号与字符集，写在 XML 第一行。下面给出一个简单的 XML 文件的结构：

```.xml
<?xml version="1.0" encoding="UTF-8"?>

<!-- 人力资源管理系统 -->
<hr>
	<employee no="3301">
		<name>云云</name>
		<age>37</age>
		<salary>3600</salary>
		<department>
			<dname>人事部</dname>
			<address>XX大厦-B105</address>
		</department>
	</employee>
	<employee no="3302">
		<name>东东</name>
		<age>50</age>
		<salary>7000</salary>
		<department>
			<dname>财务部</dname>
			<address>XX大厦-B106</address>
		</department>
	</employee>
</hr>
```

### 3，XML 语义约束之 DTD

> DTD (Document Type Definition，文档类型定义) 是一种简单易用的语义约束方式。其扩展名为 **.dtd** 。 

针对上面给出的程序，书写几条语句：

```.dtd
<!ELEMENT hr (employee+)>
<!ELEMENT employee (name,age,salary,department)>
<!ATTLIST employee no CDATA "">
....
```

上面语句看不明白不要紧，下面我们来学习一下：

- DTD 定义结点

  利用DTD中的<!ELEMENT>标签，我们可以定义 XML 文档中允许出现的节点及数量，以hrxml为例：

  - 定义 hr 节点下只允许出现 1 个 employee 子节点。

    <!ELEMENT hr (employee)>

  - employee节点下必须包含以下四个节点，且按顺序出现。

    <!ELEMENT employee (name,age,salary,department)>

  - 定义 name 标签体只能是文本，#PCDATA代表文本元素。

    <!ELEMENT name (#PCDATA)>

- DTD 定义结点数量

  如某个子节点需要多次重复出现，则需要在子节点后增加相应的描述符。

  - hr 节点下最少出现 1 个 employee 子节点。

    <!ELEMENT hr (employee+)>

  - hr 节点下可出现 0..n 个 employee 子节点。

    <!ELEMENT hr (employee*)>

  - hr 节点下最多出现 1 个 employee 子节点。

    <!ELEMENT hr (employee?)>

- XML 引用 DTD 文件

  在XML中使用 <!DOCTYPE> 标签来引用 DTD 文件。
  

  ```
  书写格式：
  <!DOCTYPE 根节点 SYSTEM "dtd文件路径">
  示例:
  <!DOCTYPE hr SYSTEM "hr.dtd" >
  ```

  *DTD 文件主要是对 XML 文件进行校验，并且两者的文件名最好相同* 

### 4，XML Schema

> XML Schema比DTD更为复杂，提供了更多功能。XML Schema提供了数据类型、格式限定、数据范围等特性。
> XML Schema是W3C标准。

### 5，DOM文档对象模型

> DOM (Document Object Model) 定义了访问和操作XML 文档的标准方法，DOM 把 XML 文档作为树结构来查看，能够通过 DOM 树来读写所有元素。

对如下的一份文档：

![image-20220529203033890](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220529203033890.png)

我们可以将它想象成为一种树结构：

![image-20220529203058460](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220529203058460.png)

#### Dom4j

- Dom4j 是一个易用的、开源的库，用于解析 XML 。它应用于 Java 平台，具有性能优异、功能强大和极其易使用的特点。（官网下载，添加到开发工具中的folder中)
- Dom4j 将 XML 视为 Document 对象。
- XML 标签被 Dom4j 定义为 Element 对象。
  

### 6，Xpath 基本表达式案例

![image-20220530105138071](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220530105138071.png)

![image-20220530105157824](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220530105157824.png)

![image-20220530105229828](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220530105229828.png)

[ ] 内含属性。

#### Xpath实验室 

![image-20220530105708889](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220530105708889.png)

![image-20220530111859081](http://rblgz07nn.hd-bkt.clouddn.com/img/blogimage-20220530111859081.png)



