---
title: "搭建图床"
date: 2022-08-08T21:00:00+08:00
tags: ["免费","github","cdn"]
toc: true
---

## 需求分析

- 使用场景

我们的文章（笔记、论文、博客）中常有出现图片的需求，以使用常见的**Markdown**编辑器 **Typora** 记笔记的场景为例，如果我们直接将图片复制粘贴至其中，会得到如下图的效果

![](https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-001.png)

可以看到图片的链接是其在**本地**的相对链接，这导致了以下的缺点

- 文章难以迁移，若作为博客发布在网络上图片**无法正确加载**
- 若**仅**本地存储无法保证数据安全
- 图片资源存储在本地，难以使用**Git**对重要的文章进行版本控制

而拥有了图床之后，图片地址将如下图所示,以**https**开头的形式存在

```url
https://gcore.jsdelivr.net/gh/AlexLiu2022/resources/img/blog-pic-bed-example-001.png
```

这样文章中只存在图片在服务器链接的**文本** 内容迁移、版本管理变得容易

## 方案对比

构建图床有多种方案 这里分析两种常见方式的利弊以证明我们技术选型的优越性

| 方案                          | 优点                   | 缺点                                                           |
| ----------------------------- | ---------------------- | -------------------------------------------------------------- |
| 图床提供商 如七牛云\ SM.MS 等 | 操作简便、速度通常较快 | 付费、有倒闭风险、数据不自主、免费版速度容量受限、迁移困难 |
| 服务器自建图床            | 数据安全自主           | 操作相对繁琐 个人服务器成本                                                               |

## 技术选型

- 使用 **GitHub** 仓库作为免费图床（请合理利用资源，不要浪费）
- 使用 **JsDelivr** 的CDN加速服务（保证对仓库资源的访问速度)
- 使用 **PicGo** 提供的自动上传服务简化操作

这一套方案的优势是：**完全免费**、速度快、操作简便、图片可同时存放在本地和云端 数据自主安全

## 具体实现

### 前置知识

1. **Git** 和 **GitHub** 的基本使用

### 分步演示

1. 在GitHub上创建一个**公开**仓库用作免费图床

    **注意** 必须是公开仓库 否则无法利用 **PicGo** 提供的自动上传服务

2. 在 **GitHub** 个人账号页面：Settings --> Developer settings --> Personal access tokens --> Generate new token --> Expiration选no expiration --> Select scopes中勾选repo --> Generate token --> 记下生成的token

3. 下载 **PicGo** 打开**图床设置**页面
    1. 打开GitHub图床页面 设为**默认图床**
    2. 设定仓库名 `username/repo_name`
    3. 设定分支名 `main`(或`master`)
    4. 设置token为上一步生成的token
    5. 指定存储路径 如`img/`
    6. 设定自定义域名 `https://gcore.jsdelivr.net/gh/username/repo_name`

4. 在自己使用的编辑器中配置自动上传服务 如 **Typora** 在设置的 image --> Image Upload Setting中, 选取Image Uploader 为 **PicGo**

5. 完成 测试效果 尽情使用自己的图床吧～