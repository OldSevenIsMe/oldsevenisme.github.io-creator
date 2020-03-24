---
title: "用hugo搭建个人博客"
date: 2020-03-24T18:31:18+08:00
draft: false
---

# 第一步：安装Hugo
1.浏览 Hugo 官方的安装指南。

进行初步了解，安装与你的操作系统对应的必要工具。

Hugo 安装指南：[https://gohugo.io/getting-started/installing/](https://gohugo.io/getting-started/installing/)

2.打开你的终端，输入与操作系统对应的 Hugo 安装命令。

3.安装完成后，输入以下命令来确认
```
hugo version
安装成功后会跳出以下代码
Hugo Static Site Generator v0.56.3-F637A1EA windows/amd64 BuildDate: 2019-07-31T12:51:49Z
```
# 第二步：新建一个Hugo网站
1.进入你想存放 Hugo 网站文件夹的目录。

2.执行以下命令来新建一个Hugo网站
```
hugo new site '你的博客名' 
```

# 第三步：选择 Hugo 主题并克隆至本地目录。
1.打开 Hugo Themes 页面，选择一个你喜欢的主题。

Hugo Themes: [https://themes.gohugo.io](https://themes.gohugo.io/)

下文以选择 ananke主题为例。

```
cd '你的博客名'            ---进入你的博客目录
git init                  ---初始化本地仓库
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke  ---将ananke主题克隆到本地
```

# 第四步：编辑配置文件
1.  在 Hugo 网站文件夹的根目录下，使用 [Visual Studio Code](https://mp.weixin.qq.com/s/lt9XzlAOzpIqPLMuUBVNLw) 打开 `config.toml` 文件。

    如果你还没用过 Visual Studio Code，建议下载安装一下，是一个很好用的开源文本编辑器，同时支持 Windows、Linux 和 macOS 操作系统。

2.  参考所选 Hugo 主题的配置说明，编辑 `config.toml` 文件。

    **注意**：`theme` 配置项指的是所选主题的名称，必须与所选主题被克隆至的目录名相同。在本例中，即 `theme = "ananke"`。

# 第五步：新建一篇文章
```
hugo new posts/文章名.md
```
编辑新建的文章，添加内容并保存。

# 第六步：本地预览网站效果。
1. 启动 Hugo server。
```
hugo server -d
```

2.使用浏览器打开 [http://localhost:1313](http://localhost:1313/) 预览。

# 第七步：构建hugo网站

在 Hugo 网站文件夹的根目录下，执行 hugo 命令来构建。
```
hugo  ---构建你的 Hugo 网站，默认将静态站点保存到 "public" 目录。
```
**注意**：Hugo 会将构建的网站内容默认保存至网站根目录的 `public/ `文件夹中。

# 第八步：将网站文件夹转换为 Git 库。
1.进入`public`目录，初始化 Git 库。
```
cd public    ---生成的 HTML 文件保存在 "public" 目录中，"public" 文件夹会被转换为 Git 库。
git init  ---初始化git仓库
```
2.查看` public `目录下的文件，会发现多了 `.git` 文件。

# 第九步：将 Git 本地库与远程仓库关联。
1.在github上创建第一个新的仓库

2.运行以下代码来进行关联
```
git remote add origin '你的远程仓库名'   ---注意是在public目录中运行
git add .   ---将改动添加到暂存区
git commit -m '备注'   ---将改动提交
git push -u origin master   ---上传到远程仓库
```

# 第十步：通过 GitHub Pages 预览 HTML

`git push`完之后再github中点击`setting`来设置在预览你的hugo博客
(![点击setting设置](https://upload-images.jianshu.io/upload_images/19233819-95a904ee3258be44.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
)

进入之后找到 `Github Pages` 然后将`Source`的`None`设置成`master branch`，之后会生成一个网址，就是你的HTML预览的网站了
![将none修改成master branch](https://upload-images.jianshu.io/upload_images/19233819-80f4f33d9098d5f5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![这是你hugo博客的网站](https://upload-images.jianshu.io/upload_images/19233819-db8e11cdd20c7a9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 接下来：之后如何添加一篇博客

之后如果要添加一篇博客，使用如下几步即可：

新建一篇文章，编辑内容。
1.本地预览网站呈现效果。
2.构建 Hugo 网站。
3.提交修改至 Git 本地库。
4.将修改推至远程库。

**恭喜！现在你已经走完了全程，拥有了一个自己构建的博客网站。**

