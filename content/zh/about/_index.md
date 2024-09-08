---
title: "About"
date: 2022-09-20T16:00:10+08:00
anchor: false
---

<center>
	<h5>
这是一个个人博客 
<br>
It's my world & has my work
	</h5>
</center>

##### 分区 

<body>
    <div class="container101">
        <div class="content101">
            <div>
                <strong>关于：</strong>
                <div class="item">本页面：基本信息与其他</div>
            </div>
            <div>
                <strong>工作：</strong>
                <div class="item">技术博客、投资相关</div>
            </div>
            <div>
                <strong>个人：</strong>
                <div class="item">各种碎碎念(中二 || 严肃)</div>
                <div class="item">请阅读 <a href="https://alex.liu.xyz/zh/useless/about-readers/">关于读者</a></div>
            </div>
            <div>
                <strong>标签：</strong>
                <div class="item">标签云 用于分类 & 检索</div>
            </div>
        </div>
    </div>
</body>

##### 说明
 本博客完全**开源**，文章在发布后可能会持续改动，可在<a href="https://github.com/AlexLiu2022/blog" target="_blank">GitHub</a>查看相关信息

菜单栏由CN切换至EN可查看英文内容（内容存在差异 不同步更新）
- 存在英文版的页面会跳转至英文版
- 不存在的页面将跳转到英文版主页

本站默认语言为英文 默认语言为中文的平行站在<a href="https://eating.work" target="_blank">这里</a>

我的其他网站[^1]请参见本页底部`Links`

##### 订阅

你可以用[^2]以下的链接免费订阅本站的RSS feed:
```url
https://alex.liu.xyz/zh/atom.xml
```

- 推荐阅读 [关于RSS Feeds](https://alex.liu.xyz/zh/useful/about-rss-feeds/)

##### 声明
**本博客一切内容均为个人观点** 相关资源若有版权问题请联系我删除 <br>

欢迎关注我的<a href="https://x.com/liu_web3" target="_blank"> 推特 / X</a> ，**祝万事胜意 !**

![](https://cdn.jsdelivr.net/gh/AlexLiu2022/resources/img/cloud.jpg)


[^1]: 笔记库、文件站、GPT镜像站等
[^2]: 通过feedly等服务或reeder等客户端

<style>
.post-body {
margin-top: 2em !important;
}
#main {
	padding-top: 88px;
}
#sections{
margin-bottom : 30px !important;
}

.container101 {
display: flex;
justify-content: center;
align-items: center;
width: 100%;
}

.content101 {
display: grid;
grid-template-columns: 1fr;
gap: 10px;
max-width: 600px;
width: 100%;
}

.content101 > div {
background-color: #f9f9f9; /* 非常淡的灰色 */
padding: 18px;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
border-radius: 8px;
}

.content101 .item {
margin-bottom: 10px; /* 调整项间距 */
}

@media (min-width: 768px) {
.content101 {
grid-template-columns: repeat(2, 1fr);
gap: 20px;
}
}
</style>

<script>
let title = document.querySelector('h1.post-title.p-name');
title.remove();
</script>