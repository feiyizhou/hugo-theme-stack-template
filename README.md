# Hugo theme stack template

本项目是以`hugo`为框架，`hugo-theme-stack`为主题，`gitalk`为评论系统的博客搭建框架模板。所有的初始文件和配置文件都已经在项目中，只需要关注博客的配置文件`config.yaml`以及通过`hugo new content/post/${moduleName}/index.md`创建`Markdown`文件即可。

新用户可以根据以下步骤进行`hugo`的安装和使用。

## 1.Install hugo

[hugo官网](https://gohugo.io)

官方文档中有`hugo`在不同系统的安装方法，但是需要安装具备扩展功能的`hugo`才能正常将`Markdown`文件生成静态页面文件（不带扩展功能的`hugo`去转化带图片的`Markdown`文件时，图片会显示异常），所以推荐直接去`github`下载安装包自行安装。

```shell
# 安装包地址
https://github.com/gohugoio/hugo/release/tag/v0.111.3

# 以ubuntu系统、amd64架构为例
wget https://github.com/gohugoio/hugo/release/tag/v0.111.3/hugo_extended_0.111.3_linux-amd64.deb

sudo dpkg -i hugo_extended_0.111.3_linux-amd64.deb
```

推荐安装最新版本，根据系统下载文件名称中带有`extended`的文件安装即可，安装完成后查看`hugo`版本信息

```shell
$ hugo version
hugo v0.111.3-5d4eb5154e1fed125ca8e9b5a0315c4180dab192+extended linux/amd64 BuildDate=2023-03-12T11:40:50Z VendorInfo=gohugoio
```

## 2.下载本项目

```shell
git clone git@github.com:feiyizhou/hugo-theme-stack-template
```

## 3.启动项目

```shell
cd hugo-theme-stack-template && hugo server
# 启动完成后，访问localhost:1313进行验证
```

本文档只是模板的使用方法，`gitalk`配置并将页面托管到`git pages`的方法可以访问[费益洲的博客](https://feiyizhoi.github.io)获取。