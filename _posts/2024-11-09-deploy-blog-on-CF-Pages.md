---
title: 【待完善】使用Cloudflare Pages部署本博客
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

Jekyll is a static site generator that transforms your plain text into beautiful static websites and blogs. It can be used for a documentation site, a blog, an event site, or really any website you like. It’s fast, secure, easy, and open-source.
Jekyll 是一个静态网站生成器，可以将纯文本转换为漂亮的静态网站和博客。它可用于文档网站、博客、活动网站或您喜欢的任何网站。它快速、安全、简单且开源。

![img](https://miro.medium.com/v2/resize:fit:875/1*kDXZA3TftVaJDSukHUsgfA.jpeg)

In this blog post, we’ll be installing and configuring Jekyll using the Chirpy theme. We will configure the site, create some pages with Markdown, and even host it for free on Cloudflare Pages.
在这篇博文中，我们将使用 Chirpy 主题安装和配置 Jekyll。我们将配置该网站，使用 Markdown 创建一些页面，甚至将其免费托管在 Cloudflare Pages 上。

> **Prerequisites 先决条件***
> -* Github Account
> *
> -* Github 帐户
> \- Cloudflare Account - Cloudflare 帐户
> \- Cloudflare registered/managed Domain Name
> \- Cloudflare 注册/管理域名

### Github

Visit the [Chirpy Template](https://github.com/cotes2020/chirpy-starter)
访问[Chirpy 模板](https://github.com/cotes2020/chirpy-starter)

- Click on the **user this template** & **create a new repository**
  单击**此模板的用户**并**创建一个新存储库**
- Give the repository a name and click on **create repository**
  为存储库命名并单击**创建存储库**

### Cloudflare

Now the template is ready we will build the first version of the site to make sure everything is ready to go!
现在模板已准备就绪，我们将构建网站的第一个版本，以确保一切准备就绪！

- Go to [https://dash.cloudflare.com](https://dash.cloudflare.com/)
  前往[https://dash.cloudflare.com](https://dash.cloudflare.com/)
- Go to *Workers & Pages*
  转到*工作人员和页面*
- Click **Create**
  单击**创建**
- Go to **pages** and **connect to git**
  转到**页面**并**连接到 git**
- Link your github accout if needed
  如果需要，链接您的 github 帐户
- Choose your repository you just made and click **begin setup**
  选择您刚刚创建的存储库，然后单击**开始设置**
- In the build setting choose for **Jekyll** as framework
  在构建设置中选择**Jekyll**作为框架

Add the environment variables
添加环境变量

- name: **BUNDLE_WITHOUT**
  名称： **BUNDLE_WITHOUT**
- value: **""**
  取值： **""**
- Click save and deploy 单击保存并部署

![img](https://miro.medium.com/v2/resize:fit:875/1*rnMO08Dog1FrXff8MliXPA.png)

Now Cloudflare will clone your GitHub repro, build the website and publish it.
现在，Cloudflare 将克隆您的 GitHub 副本、构建网站并发布它。

If successful click **continue project**
如果成功点击**继续项目**

![img](https://miro.medium.com/v2/resize:fit:875/1*wle5S4S8gJ2Bxaa_wkgLqA.png)

You will get a generate domain name like **medium-test-em9.pages.dev**.
您将获得一个生成域名，例如**medium-test-em9.pages.dev** 。

![img](https://miro.medium.com/v2/resize:fit:875/1*zdPms4i23urc0mQlz35l2g.png)

> \- You can build up to 500 times per month on the Free plan
> \- 免费计划每月最多可构建 500 次
> \- It might take a few minutes before the dns works.
> \- DNS 可能需要几分钟才能工作。

#### Custom Domain 自定义域

As we want the website to user your domain name we will link it to the name.
由于我们希望网站使用您的域名，因此我们会将其链接到该名称。

- Click Custom Domain 单击自定义域
- Go to **Set up a Custom Domain**
  转到**设置自定义域**
- Enter the name click **contintue**
  输入名字点击**继续**
- Check the information and click **Activate Domain**
  检查信息并点击**激活域名**

It will create a **CNAME** DNS record for your name to the generate name earlier.
它将为您的名称创建一条**CNAME** DNS 记录，以生成之前的名称。

### Set up the Blog 设置博客

Now have it all up and running, we will need to fill it with content. Looks a bit empty now.
现在一切都已启动并运行，我们需要填充内容。现在看上去有点空虚。

#### Clone repository 克隆存储库

After creating a site based on the template, clone your repo to a computer with Git installed.
基于模板创建站点后，将存储库克隆到安装了 Git 的计算机。

```
git clone git@<YOUR-USER-NAME>/<YOUR-REPO-NAME>.git
cd YOUR-REPO-NAME
```

#### Adjust information 调整信息

In the `_config.yml` We will need to customize some information to give it the correct name and logo etc.
在`_config.yml`中，我们需要自定义一些信息以赋予其正确的名称和徽标等。

```
nano _config.yml
```

- **title** - Title of the Website
  **title** - 网站标题
- **tagline** - Line to be shown under the name
  **标语**- 显示在名称下方的行
- **timezone** - Change it to your timezone
  **时区**- 将其更改为您的时区
- **avatar** - Location for your logo, it must be in /assests/path/you/want
  **头像**- 您的徽标的位置，必须位于 /assests/path/you/want 中
- **name -** This will be the name shown as author with your articles
  **姓名 -**这将是您的文章中显示为作者的姓名

> Don't forget to upload the image to the folder specified. You can also set a URL to a image
> 不要忘记将图像上传到指定的文件夹。您还可以设置图像的 URL

### Make Post 发帖

Jekyll uses a naming convention for [pages and posts](https://jekyllrb.com/docs/posts/).
Jekyll 对[页面和帖子](https://jekyllrb.com/docs/posts/)使用命名约定。

Create a file in **_posts** with the format **YEAR-MONTH-DAY-title.md**
在**_posts**中创建一个格式为**YEAR-MONTH-DAY-title.md**的文件
For example: 例如：
`2024-06-18-first-post.md`

All blog post files must begin with [front matter](https://jekyllrb.com/docs/front-matter/) which is typically used to set a layout or other meta data. For a simple example this can be used:
所有博客文章文件必须以通常用于设置布局或其他元数据的[前言](https://jekyllrb.com/docs/front-matter/)开始。对于一个简单的例子，可以使用：

```
---
layout: post
title:  "Welcome to Jekyll!"
---
# Welcome
**Hello world**, this is my first Jekyll blog post.
I hope you like it!
```

### Publish post 发布帖子

As the website data lives in the GitHub repository, Cloudflare watches the repository. With every **commit** or **merge** it will rebuild the website and publish the new version automatically.
由于网站数据位于 GitHub 存储库中，Cloudflare 会监视该存储库。每次**提交**或**合并**时，它都会重建网站并自动发布新版本。

![img](https://miro.medium.com/v2/resize:fit:794/1*Jg7vRvAodUdv92KAL5qlzA.png)

CI/CI Flow CI/CI 流程

All you need to do this run these commands
您只需运行这些命令即可

```
git add .
git commit -m "First Post"
git push
```

Cloudflare will now rebuild the website and publisch the new version. You can watch the progress if you want on the Cloudflare Workers & Pages under **Deployments.**
Cloudflare 现在将重建网站并发布新版本。如果需要，您可以在**部署下的 Cloudflare Workers & Pages 上查看进度。**

The results: 结果：

![img](https://miro.medium.com/v2/resize:fit:875/1*rm3nyNOyzwPf7CpFKiPPZA.png)

Main Page 主页

![img](https://miro.medium.com/v2/resize:fit:875/1*4JHB9EVFwD384FsfX8hMFw.png)

Post Page 帖子页面

### Preview build 预览版本

While writing a post sometimes want to try out something new before everyone sees it on your site. Cloudflare Pages as the option to use *Preview builds.* These builds are made for other branches in your Github repository then the master one.
在撰写帖子时，有时想在每个人都在您的网站上看到新内容之前尝试一些新内容。 Cloudflare Pages 作为使用*预览版本的选项。*这些构建是为 Github 存储库中的其他分支（然后是主分支）构建的。

### Make Branch in Github 在Github上创建分支

- Go back to your Github repository
  返回您的 Github 存储库
- Click on **branches**
  点击**分支**
- Click on **New Branch**
  点击**新建分支**
- Give a name like *test*
  起一个名字，比如*测试*

### Cloudflare pages Cloudflare 页面

In your Cloudflare Pages deployment;
在您的 Cloudflare Pages 部署中；

- Go to **Settings**
  前往**“设置”**
- Go to **Build & Deployments**
  转到**构建和部署**
- Click on **Configure Preview Deployments**
  单击**配置预览部署**
- Select Custom branches 选择自定义分支
- Fill in the branch name we just made under **Include Preview branches**
  在**Include Preview Branches**下填写我们刚刚制作的分支名称
- Click Save 单击“保存”

Now Cloudflare Pages will build the blog based of that branch. If you like the changes made in the test branch you can create a pull request to move them to the master branch so everybody can see them :).
现在，Cloudflare Pages 将基于该分支构建博客。如果您喜欢测试分支中所做的更改，您可以创建拉取请求以将它们移动到主分支，以便每个人都可以看到它们:)。

Congrats, you have now build and published your blog with Jekyll and Cloudflare pages!
恭喜，您现在已经使用 Jekyll 和 Cloudflare 页面构建并发布了您的博客！

---

原文地址：https://medium.com/@svenvanginkel/build-a-blog-with-jekyll-chirpy-on-cloudflare-pages-f204bc538af9

由 Gemini 1.5 pro 辅助翻译