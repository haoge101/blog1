---
title: "Angular 提交规范"
date: 2024-11-09 17:51:00 +0800
categories: [Study] # 目前有 Demo, Tutorial, Tech, Study
tags: [Angular, Git]
author: Zwei  # 或 authors: [Zwei, another_author]
description: "规范的 git commit 信息"
image:
  path: https://testingcf.jsdelivr.net/gh/bestZwei/imgs@master/picgo/3a9282f87f892c286c9a9ccebe9c95dd_1679484529_216.png
permalink: '/w/Angular'  # 自定义永久链接
pin: false # 置顶文章
toc: true # 显示目录
comments: true # 允许评论
math: true # 启用数学公式
mermaid: true # 启用 Mermaid 图表
render_with_liquid: false # 禁用 Liquid 渲染
media_subpath: /blog/assets/ # 资源路径前缀
---

---

#### 格式

Angular 提交规范是一种约定俗成的提交信息格式，旨在使提交历史更加清晰和有序。提交信息通常分为类型、范围和简短描述三个部分，格式如下：

```
<类型>(<范围>): <简短描述>
```

##### 1. 类型（Type）

用于描述提交的性质，常见类型有：

- **feat**: 新功能（A new feature）
- **fix**: 修复 bug（A bug fix）
- **docs**: 文档变更（Documentation only changes）
- **style**: 代码样式变更，不影响代码意义（Changes that do not affect the meaning of the code, such as white-space, formatting, missing semi-colons, etc.）
- **refactor**: 重构代码（A code change that neither fixes a bug nor adds a feature）
- **test**: 测试相关（Adding missing tests or correcting existing tests）
- **perf**: 提高性能的代码
- **chore**: 其他杂项（Other changes that don't modify src or test files）

##### 2. 范围（Scope）

描述提交所涉及的范围，可以是任何与提交相关的内容，通常是文件名或模块名。例如：

- **login**: 涉及登录功能
- **api**: 涉及API相关的修改
- **readme**: 涉及README文档的修改

##### 3. 简短描述（Subject）

对提交的简要描述，要求清晰明了，简洁扼要。通常建议不超过50个字符，并且使用祈使句形式。例如：

- **add new login feature**
- **fix issue with API request**
- **update installation instructions**

##### 4. 脚注（Footer）
   脚注用于记录本次提交的一些重要信息，如与某个 issue 相关或者是破坏性的变更。

  ` Issue #12`

#### 示例

以下是一些符合Angular提交规范的示例：

```
feat(login): add new login feature
fix(api): fix issue with API request
docs(readme): update installation instructions
style(app): format code according to new style guide
refactor(user): simplify user authentication logic
test(auth): add unit tests for authentication service
chore(deps): update project dependencies
```

#### 其他注意事项

- **详细描述**（可选）：在简短描述之后，可以添加更详细的描述，通常放在提交信息的正文部分。
- **关联问题**（可选）：如果提交是为了修复某个问题，可以在提交信息中引用问题编号，例如`fixes #123`。

通过遵循这些规范，可以使项目的提交历史更加清晰，便于团队协作和代码审查。

