---
title: Hexo安装部署教程
comments: true
tags: 无标签
message: 请输入密码，才能继续查看
date: 2019-08-20 22:10:09
password: 
---
# Hexo-Installation-Tutorial
# Hexo安装教程
- 教程声明:本篇教程所有涉及到的资源和引用，均由原网站保留解释权
- 本文作者不会承担任何安装为你带来的烦恼，但是会给你们做疑难解答，请到[Issues](https://github.com/dabai2017/Hexo-Installation-Tutorial/issues)提问。
- 本文发行版只有中文版，后续会翻译为其他语言版本

# hexo官方站
https://hexo.io/zh-cn/


# 欢迎
欢迎观看hexo完整安装教程，我是作者大白2017
- 由于win和Android这两种平台，只是所需软件不同，其他操作基本相似，所以本篇教程只讲win平台，当然，本篇教程理论上也适用于其他操作系统

# 下载所需

### Windows所需
[git桌面版](https://www.lanzous.com/i5ch0qf)  
[node.js](https://www.lanzous.com/i5cedih)

### Android所需
[Termux终端](https://www.lanzous.com/i5ceiaj)

### hexo完整包
[通过git拉取](https://gitee.com/dabai2017/hexo_package.git)  
[蓝奏云下载](https://www.lanzous.com/b881565)

### 需要账户
- 这篇教程讲的是**将完整hexo部署到git代码托管服务**。所以你需要一个[github](https://github.com)账号，当然也可以是[码云](https://gitee.com)的账号。

# 部署教程开始
1. 安装node.js
2. 安装git客户端
3. git客户端分为bash和gui两部分，下面所讲的git是bash命令行
4. 使用git输入下面命令

```
git config --global user.name "git用户名"
git config --global user.email "git绑定的邮箱地址"
ssh-keygen -t rsa -C "git绑定的邮箱地址"
cd ~/.ssh
cat id_rsa.pub
```

6. 这样就可以得到**本机ssh公钥**
7. 打开码云的**设置-安全设置-ssh公钥**
8. 标题随便写，内容填**本机的ssh**
9. 点击确定保存
10. 然后在码云创建一个**仓库(最好命名为blog)**，拿到**ssh链接**
11. 现在把刚刚下载的**hexo-chic修改版.zip**解压，如果是拉取的git就不需要解压了
12. 打开**/hexo-chic/_config.yml**，定位到最后一部分，把刚刚的ssh链接复制到那里，然后把root的值改成仓库名，不然找不到目录也是404
13. 打开git输入 npm install 安装所有插件就可以直接部署hexo到码云了，但码云部署完需要手动更新一下。
14. 打开git输入以下命令就可以部署了

```
cd /hexo-chic
hexo g
hexo d
```

15. 然后打开**码云-你的博客仓库-服务-Gitee Pages**，没有打开的就开启，已经**开启**的后续每次部署完都要手动点击**更新**才能生效，如果已经就绪，就会显示**已开启 Gitee Pages Pro 服务，网站地址： https://你的用户名.gitee.io/blog **
16. 你可以点击那个网站地址来查看你的博客最初的样子


# 总结
5步：环境准备，下载hexo包，设置ssh公钥，设置ssh链接和root目录，最后生成部署。