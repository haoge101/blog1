---
title: 使用Cloudflare Pages部署本博客
description: >-
  这是非常棒的Jekyll博客项目，可以借助Github Pages、Vercel、netify、Cloudflare Pages等部署...
author: Zwei
date: 2024-11-09 01:23:00 +0800
categories: [Blogging, Tutorial]
tags: [getting started]
pin: false
media_subpath: '/posts/deploy-blog'
---

### 使用 Jekyll 和 Chirpy 在 Cloudflare Pages 上构建博客

Jekyll 是一个静态网站生成框架，可以将纯文本转换为漂亮的静态网站和博客。它可用于文档网站、博客、活动网站或您喜欢的任何网站。它快速、安全、简单且开源。

![](https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/20241113193834.png)

在这篇博文中，我们将使用 Chirpy 主题安装和配置 Jekyll。我们将配置该网站，使用 Markdown 创建一些页面，甚至将其免费托管在 Cloudflare Pages 上。

> **请先准备好**
> 
> + Github 帐户
> + Cloudflare 帐户
> + Cloudflare 注册/管理的域名
> + Git 环境
> + Node.js 环境

### Github

访问 [Chirpy 模板](https://github.com/cotes2020/chirpy-starter)

- 单击fork此模板
- 为存储库命名并单击创建存储库

### Cloudflare

现在模板已准备就绪，我们将构建网站的第一个版本，以确保一切准备就绪！

- 前往 [dash.cloudflare.com](https://dash.cloudflare.com/)
- 转到 Workers & Pages
- 单击创建
- 转到 Pages 并连接到 git
- 如果需要，链接您的 github 帐户
- 选择您刚刚创建的存储库，然后单击开始设置
- 在构建设置中选择 Jekyll 作为框架

**添加环境变量**

- 变量名： `BUNDLE_WITHOUT`
- 取值： `""`
- 单击保存并部署

现在，Cloudflare 将克隆您的 GitHub 副本、构建网站并发布它。

如果成功，您将获得一个生成域名，例如 xxx.pages.dev 。

> + 免费计划每月最多可构建 500 次
> + DNS 可能需要几分钟才能工作

#### 自定义域

- 单击自定义域
- 转到设置自定义域
- 输入你的域名或者子域名点击继续
- 检查信息并点击激活域名

这将为您的名称创建一条 CNAME 记录，以生成之前的名称。

### 设置博客

Now have it all up and running, we will need to fill it with content. Looks a bit empty now.
现在一切都已启动并运行，我们需要填充内容。现在看上去有点空虚。

#### 克隆存储库到本地

基于模板创建站点后，将存储库克隆到安装了 Git 的计算机。

```
git clone git@<YOUR-USERNAME>/<YOUR-REPO-NAME>.git
```

#### 初始化

###### 请确保你的计算机有 [Node.js](https://nodejs.org/zh-cn/download/package-manager) 环境

务必进行这一步，否则你的博客站点许多功能无法使用；

```bash
# 根据你的系统，在 CMD 窗口运行 init 脚本
bash tools/init
# 或者
bash tools/init.sh
```

这一步将会在你的目录中创建一些配置文件，请检查 ` assets/dist/*.min.js `

如果没有这些文件，你需要运行下面的代码：

```bash
npm install && npm run build
bundle update
```

#### 调整信息

在`_config.yml`中，我们需要自定义一些信息以赋予其正确的名称和徽标等。

```
nano _config.yml
```

- 网站标题
- 副标题
- 时区
- 徽标
- 姓名
- 社交媒体和邮箱
- URL
- permalink（博文链接格式）
- ......

> 不要忘记将图像上传到指定的文件夹。你的图片可以存放在 /assets/img/ 目录下，引用方式为 `/assets/img/img123.pmg `；您还可以设置图像的 URL，这个项目支持 CORS。

### Make Post 发帖

+ 格式参考：
  `2024-06-18-first-post.md`

+ 所有博客文章文件必须以通常用于设置布局或其他元数据的 [front-matter ](https://jekyllrb.com/docs/front-matter/)开始。对于一个简单的例子，可以使用：

```
---
layout: post
title:  "Welcome to Jekyll!"
---
# Welcome
**Hello world**, this is my first Jekyll blog post.
I hope you like it!
```

更详细的 front-matter 格式请参考 https://zwei.de.eu.org/w/write-a-new-post/

### 作者设置

编辑`/_data/author.yml` 文件

此目录下另外三个 .yml 文件也可以根据需求修改。

### 发布博文

将你的 Markdown 格式的博文存放在 `_Post` 文件夹，然后提交到仓库。

```
git add .
git commit -m "First Post"
git push
```

Cloudflare 现在将重建网站并发布新版本。如果需要，您可以在 Pages 项目上查看进度。

### 修改 About 页面

编辑 `/_tabs/about.md` 文件

### 更新配色方案

`/_sass/colors` 下有四个文件，分别生成亮暗模式下的主页面配色、代码块配色。

---

参考文献：https://medium.com/@svenvanginkel/build-a-blog-with-jekyll-chirpy-on-cloudflare-pages-f204bc538af9
