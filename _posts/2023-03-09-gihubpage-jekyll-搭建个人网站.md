---
layout: post
title: 使用GitHub+Jekyll搭建个人博客
date: 2023-03-09 11:29:08 +0800
tags: [Jekyll, GitHub]
---



欢迎您的到来，这里是小华的一个小网站 O(∩_∩)O~

{: .note .info}
gihubPage +jekyll 搭建个人网站

## 1、下载ruby、gem、kekyll (windows)

https://blog.csdn.net/qq_34967770/article/details/110098826



## (1)自己搭建网页

>参考：
>
>[(74条消息) 如何使用Jekyll在GitHub Pages上搭建网站（个人博客）_jekyll github pages_zhonguncle的博客-CSDN博客](https://blog.csdn.net/qq_33919450/article/details/127859193)

### 1、创建gihub仓库：

username.github.io

项目内部为空

### 2、创建本地仓库(用于编写、修改源文件、添加文章)

#### （1）克隆远程仓库

- 会**自动设置好远程仓库名为origin**

```
	//克隆仓库项目
	git clone 仓库地址	
	//必须进入目录
	cd my_repo_name
```

#### (2)修改文件

参考如下：

[(74条消息) 如何使用Jekyll在GitHub Pages上搭建网站（个人博客）_jekyll github pages_zhonguncle的博客-CSDN博客](https://blog.csdn.net/qq_33919450/article/details/127859193)

#### **本地文件结构如下**：

<img src="D:\Typora_IMAGE\image-20230309194728379.png" alt="image-20230309194728379" style="zoom:67%;" /> 



#### 修改index.html文件

```

<!DOCTYPE html>
<html>
	<head>
	    <meta charset="utf-8">
	    <title>小华的主页_(:з」∠)_</title>
  	</head>
  	<body>
        <h1>很高兴见到您 🙂 </h1>
    	<h1>你好呀~这里是小华的主页，暂时空空如也~ 🥵 </h1>
		<h1>测试git！ </h1>
  	</body>
</html>
```



#### jekyll build之后生成站点文件docs：

<img src="D:\Typora_IMAGE\image-20230309195001567.png" alt="image-20230309195001567" style="zoom:50%;" /> 



#### （3）提交到远程仓库

<img src="D:\Typora_IMAGE\image-20230309195300270.png" alt="image-20230309195300270" style="zoom:50%;" /> 



```
git push [alias] [branch]
```

以上命令将你的 [branch] 分支推送成为 [alias] 远程仓库上的 [branch] 分支，实例如下

```
$ git push origin master    # 把本地的master分支 推送到名字为origin的 远程仓库的master分支
```

>注意报错： error: src refspec master does not match any
>
>**如果在github的remote上已经有了文件，会出现错误。此时应当先pull一下，即：**
>
>```html
>$ git pull origin master
>```
>
>然后再进行：
>
>```html
>$ git push origin master
>```



### [重要]3、本地预览效果

- #### 在本地仓库生成docs后，使用指令：

> jekyll server

<img src="D:\Typora_IMAGE\image-20230309200558766.png" alt="image-20230309200558766" style="zoom:67%;" /> 

- #### 访问4000端口：

<img src="D:\Typora_IMAGE\image-20230309200621385.png" alt="image-20230309200621385" style="zoom:50%;" /> 



### 4、设置站点相关

#### (1)设计解析文件

- 如果是**root**，就直接解析index.html

- **否则解析的是，使用jekyll生成的docs文件夹的文件(站点)**

<img src="D:\Typora_IMAGE\image-20230309195505346.png" alt="image-20230309195505346" style="zoom:50%;" /> 

#### (2)域名解析

[GitHub+Hexo 搭建个人网站详细教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/26625249)

- 使用ping来得到自己的io网址的ip

<img src="D:\Typora_IMAGE\image-20230308232158608.png" alt="image-20230308232158608" style="zoom:67%;" /> 



<img src="D:\Typora_IMAGE\image-20230308232212309.png" alt="image-20230308232212309" style="zoom:67%;" />  





### 5、效果(解析docs)

> 有空再试试多做做，按照上面的网址，学习jekyll语法

<img src="D:\Typora_IMAGE\image-20230309195706267.png" alt="image-20230309195706267" style="zoom:50%;" /> 



## (2)使用模板

### 模板网站

http://jekyllthemes.org/

### 1、获取模板

(1)fork

- fork好看的模板，创建新仓库，仓库命名为： username.github.io

- 然后拉取到本地

或者：

(2)本地操作

- 先如上，创建远程空仓库，拉取到本地;
- 下载好看的模板到本地仓库

<img src="D:\Typora_IMAGE\image-20230309204236395.png" alt="image-20230309204236395" style="zoom:50%;" /> 

### 2、修改模板文件

参考： http://t.csdn.cn/dk3RQ

- 前提是已经把远程仓库同步到本地（内容都是别人的模板）

- #### 删除所有的_posts文件夹的文章，进行替换

  - 格式： **日期-文章名**

- #### 在_config.yml文件中配置其它文件等



### 3、预览

- #### 本地预览：在本地仓库生成docs后，使用指令：

> jekyll server

<img src="D:\Typora_IMAGE\image-20230309200558766.png" alt="image-20230309200558766" style="zoom:67%;" /> 

- #### 访问4000端口：

<img src="D:\Typora_IMAGE\image-20230309204449479.png" alt="image-20230309204449479" style="zoom: 25%;" />  





## 2、编写文章

### 编写文章

`_posts` 目录下放文章文件

文件名格式为：YEAR-MONTH-DAY-title.md

> - `_drafts` 草稿目录，文件名格式为：title.md，即不加日期前缀，如果需要预览草稿，使用 *--drafts* 选项运行 *jekyll serve* 或 *jekyll build*
>
> *** 尽量避免使用中文文件名, 具体目录结构请参考: [官方文档](http://jekyll.com.cn/docs/structure/)**

每篇文章都必须以参数：

> ```
> ---
> layout: post
> title: 使用GitHub+Jekyll搭建个人博客
> date: 2016-11-21 11:29:08 +0800
> tags: [Jekyll, GitHub, 教程]
> ---
> ```

作为头部信息，layout为布局格式；title为显示的文章名；date为显示的发布日期；tags为文章分类标签

### 生成并推送

- md格式写文章，并放入_posts文件夹，然后进行push到仓库
- 不需要`jekyll build`？



## Git相关

[Git 教程 | 菜鸟教程 (runoob.com)](https://www.runoob.com/git/git-tutorial.html)

[Git - 远程仓库的使用 (git-scm.com)](https://git-scm.com/book/zh/v2/Git-基础-远程仓库的使用)

> `git clone` 命令**自行添加远程仓库并设置默认名字origin**的
>
> 自己添加： 运行 `git remote add <shortname> <url>` 添加一个新的远程 Git 仓库，同时**指定一个方便使用的简写**：
>
> ```console
> $ git remote
> origin
> $ git remote add pb https://github.com/paulboone/ticgit
> ```

如果你使用 `clone` 命令克隆了一个仓库，命令会自动将其添加为远程仓库并默认以 “origin” 为简写。 

所以，`git fetch origin` 会抓取克隆（或上一次抓取）后新推送的所有工作。 

必须注意 `git fetch` 命令只会将数据下载到你的本地仓库——它并不会自动合并或修改你当前的工作。 当准备好时你必须手动将其合并入你的工作。



### Push

```
git init //初始化一个git的本地仓库
 
git add README.md //将我的文件装上武器，准备发射
 
git commit -m “first commit” //第一次发射，我的README.md 宝贝已经成功进入到本地仓库
 
git remote add Ceres your_first_git_address //将第一个git address命名为Ceres  （一般把远程的叫做origin）
 
git push -u Ceres master //注意咯，我要向远端木星发射了，太远了，一定要用push，很费劲的赶脚
//master是本地分支的名字
```



### 小结

1、clone

2、进入仓库文件夹

3、修改

4、git pull -u origin

5、验证一些东西（用code最方便！）





## 设置网页文件

### 1、调整链接

-  \ _data\social_media.yml

修改其中需要的链接;

-  \ _includes\social_media.yml 在这里设置：

![image-20230309210646372](D:\Typora_IMAGE\image-20230309210646372.png) 

- 在以下文件中设置URL：

<img src="D:\Typora_IMAGE\image-20230309210350363.png" alt="image-20230309210350363" style="zoom:50%;" /> 
