---
title: "搭建图床"
date: 2022-08-08T21:00:00+08:00
tags: ["免费","工具","工作流","github","cdn"]
toc: true
---

## 需求分析

- 使用场景

我们的文章（笔记、论文、博客等）中常需要图片。以使用常见的**Markdown**编辑器 **Typora** 记笔记的场景为例，如果我们直接将图片复制粘贴至其中，会得到如下的效果

![](https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-001.png)

可以看到图片的链接是其在**本地**的相对链接，这导致了以下的缺点

- 文章难以迁移，若作为博客发布在网络上图片**无法正确加载**
- 若**仅**本地存储无法保证数据安全
- 图片资源存储在本地，难以使用**Git**对重要的文章进行版本控制

有了图床，图片地址将如下，以**https**开头的链接形式存在

```url
https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-001.png
```

这样文章中只存储图片在服务器的链接**文本** 内容迁移、版本管理变得容易

## 方案对比

构建图床有多种方案 这里分析两种常见方式的利弊以证明我们技术选型的优越性

| 方案                          | 优点                   | 缺点                                                           |
| ----------------------------- | ---------------------- | -------------------------------------------------------------- |
| 图床提供商 如七牛云\ SM.MS 等 | 操作简便、速度通常较快 | 付费、有倒闭风险、数据不自主、免费版速度容量受限、迁移困难 |
| 服务器自建图床            | 数据安全自主           | 操作相对繁琐 个人服务器成本                                                               |

## 技术选型

- 使用 **[GitHub](https://github.com/)** 仓库作为免费图床（请合理利用资源，不要浪费）
- 使用 **[jsDelivr](https://www.jsdelivr.com/)** 的免费CDN加速服务（保证对仓库资源的访问速度)
- 使用 **[PicGo](https://picgo.github.io/PicGo-Doc/zh/)** 提供的自动上传服务简化操作

这一套方案的优势是：**完全免费**、速度快、操作简便、图片可同时存放在本地和云端 数据自主安全

## 具体实现

### 前置知识

1. **[Git](https://git-scm.com/)** 和 **GitHub** 的基本使用

### 分步演示

1. 在GitHub上创建一个**public**仓库用作免费图床

    **注意** 必须是公开仓库 否则无法利用 **PicGo** 提供的自动上传服务

2. 生成`token`： 
    - 在 **GitHub** 个人账号页面：`Settings` --> `Developer settings` 
    - --> `Personal access tokens` --> `Generate new token` 
    - --> `Expiration`选`no expiration` --> `Select scopes` 勾选 `repo` 
    - --> `Generate token` --> 记下生成的`token`

>相关操作对应的github界面
![](https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-002.png)


3. 下载 **[PicGo](https://picgo.github.io/PicGo-Doc/zh/)** 打开 **图床设置** 页面：
    1. 打开GitHub图床页面 设为**默认图床**
    2. 设定仓库名 为`username/repo_name`(替换为你自己的GitHub用户名/你在步骤1创建的仓库名)
    3. 设定分支名为 `main`(或`master`)
    4. 设置token为上一步生成的token
    5. 指定存储路径 如`img/`
    6. 设定自定义域名 `https://gcore.jsdelivr.net/gh/username/repo_name`

>图床设置页面
![](https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-003.png)


4. 启用自动上传服务

    在自己使用的编辑器中配置自动上传服务 如 **Typora** 在设置项 image --> Image Upload Setting中, 设置Image Uploader 为 **PicGo**, 此外强烈推荐使用[**Obsidian**](https://obsidian.md/)编辑器，可配合插件使用以获得最佳体验，其他编辑器配置请自行[搜索](https://www.bing.com)
    
>obsidiain Image auto upload Plugin界面
![](https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-004.png)


5. 完成 测试效果 尽情使用自己的图床吧～