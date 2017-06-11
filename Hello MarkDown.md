# 标题

# 标题1 #后加空格 #

## 标题2 ##

### 标题3 ###

#### 标题4 ####

##### 标题5 #####

标题1：用三个等号===

===

标题2：用三个横线---

---



# 段落

文本文本文本加入两个空格表示两个段落  

文本文本文本两个空格换行  



# 强调

*斜体*一个星号/下划线   

**加粗两个星号 ** 

***斜体加粗三个星号 *** 

--删除线--   GFM



# 列表

- 一级无序列表 横杠-/星号*

  - 二级无序列表 两个空格/Tab

    - 三级无序列表

      ​

1. 有序列表 1.
2. 有序列表 自动序号重排
3. 有序列表



# 链接

<http://baidu.com>  

### 内嵌式链接

- 外部链接

  `[百度首页](http://www.baidu.com)`

  [百度首页](http://www.baidu.com)

- 内部链接

  - 仓库的其他部分

    `[Hello Git][Hello Git.md]`

    [Hello Git][Hello Git.md]

  - 本文档的其他部分

    `[代码块](Hello MarkDown.md#代码块-demo)`

    [代码块](Hello MarkDown.md#代码块-demo)

### 引用式链接

​	外部链接：[百度][baidu]、[百度首页]

​	外部链接：[百度首页](baidu)

​	仓库的其他部分：[Hello Git](Hello Git)

​	本文档的其他部分：[代码块]



# 图片

加感叹号就直接显示链接的图片、不加感叹号就是文字链接

- 外部图片

  `![alt](url "text")`

![MOU](http://0.pic.pc6.com/thumb/up/2014-6/201462685932_128_128.jpg "MOUMOUMOUMOU")

- 内部图片

  `![](images/MarkDown.png)`

  ![](images/MarkDown.png)

- 引用图片

  `![MOU](MOU)`

  ![MOU](MOU)

  `![MarkDown](MarkDown)`

  ![MarkDown](MarkDown)

<!-- 本文档引用的连接 -->

[百度首页]: http://www.baidu.com
[baidu]: http://www.baidu.com
[Hello Git]: HelloGit.md
[代码块]: HelloMarkDown.md#代码块-demo
[MOU]: http://0.pic.pc6.com/thumb/up/2014-6/201462685932_128_128.jpg
[MarkDown]: images/MarkDown.png



# 引用

> 引用  

​		——出自《》

> 引用
>
> > 嵌套引用
> >
> > > 嵌套嵌套引用



# 代码块 demo

- 行内代码

  代码`var a = 10`,打印`console.log(a)`

- 块式代码

  ```html
  <body>
  <div id = "title">
  <h1>MarkDown</h1>
  <img src=""> 
  </div>
  </body>
  ```

  ```javascript
  var a = 10;
  console.log(a);
  ```

  ```
  ​```javascript
  var a = 10;
  console.log(a);
  ​````
  ```





# 水平分割线

三个横杠-/三个星号*/三个下划线_

---

***

___



# HTML代码

<p align='center'>Hello World!</p>



# 表格


|   版本 | 修改内容 | 修改时间     |
| ---: | :--: | :------- |
| v0.1 | 需求描述 | 2016-1-1 |



<!-- | 这 | 是 | 表 | 头 | -->

<!-- | ---: | :---: | :---: | ---: | -->

<!-- | 1 | 2 | 3 | 4 | -->

<!-- | 1111 | 2222222 | 3333333 | 4 | -->

 这 | 是 | 表 | 头 

 ---: | :---: | :---: | ---: 

 1 | 2 | 3 | 4 

 1111 | **2222222** | *3333333* | 4 



# GFM

GitHub Flavored MarkDown

- task list  - [ ]  /  - [x] 

  - [ ] item1


  - [x] item2


  - [ ] item3


  - [x] item4

- emoji表情符号  :emoji code:

  http://www.emoji-cheat-sheet.com

  :+1:

  :octocat:

  ​

  ​

# 有道云笔记画图

```
graph TD
S[开始]-->A
A[用户管理]-->B{是否注册}
B-->|是|B1(输入用户名密码)
B-->|否|B2(注册)
B2-->C[注册完成]
C-->B
B1-->D[登录]
D-->E[结束]
```

```
gantt
title 产品计划表
dateFormat YYYY-MM-DD
section 前期
需求分析: 2016-11-11, 8d
section 中期
编码开发: 2016-11-19, 15d
section 后期
系统测试: 2016-11-26, 15d
```
