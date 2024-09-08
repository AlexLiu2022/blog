---
title: "About"
date: 2022-09-22T12:22:22+08:00
anchor: false
---

<center><span style="font-size:28px">This site is a personal blog.   <br>It's my world & has my work</span></center>

<h5> Sections </h5>

<body>
    <div class="container101">
        <div class="content101">
            <div>
                <strong>About:</strong>
                <div class="item">This page, basic info & others</div>
            </div>
            <div>
                <strong>Work:</strong>
                <div class="item">Tech blogs, investment related</div>
            </div>
            <div>
                <strong>Self:</strong>
                <div class="item">All kinds of fragments in mind</div>
                <div class="item">Serious &nbsp;|| &nbsp;Pretentious articles</div>
                <div class="item">Please read <a href="https://alex.liu.xyz/useless/about-readers/">About Readers</a> first</div>
            </div>
            <div>
                <strong>Tags:</strong>
                <div class="item">Tag cloud used for classification</div>
                <div class="item">(Actually it's for being cool ...)</div>
            </div>
        </div>
    </div>
</body>

<h5> Some Tips </h5>

 This blog is completely open source and its contents are subject to change after publication, which are tracked on <a href="https://github.com/AlexLiu2022/blog" target="_blank">GitHub</a>.

Switch from EN to CN in the menu bar to view Chinese contents (contents are different and not updated synchronously)

- Pages that exist in Chinese  will be redirected to the Chinese version
- Other pages will be redirected to the Chinese version's homepage

Default language of this site is English. The Chinese-first parallel site is <a href="https://eating.work" target="_blank">here</a>.

For my other websites[^1] please see `Links` at the bottom of this page.

<h5> Subscribe </h5>

You can subscribe to this site's RSS feed for free using the link below[^2]:

```url
https://alex.liu.xyz/atom.xml
```

<h5> Declaration </h5>

**Everything on this blog is my personal opinion.** If there is a copyright problem with related resources, please contact me to delete.<br>

Welcome to my <a href="https://x.com/liu_web3" target="_blank">Twitter / X</a>. 

**Have a nice day!**

![](https://cdn.jsdelivr.net/gh/AlexLiu2022/resources/img/cloud.jpg)

[^1]: Knowledge Library, File List, ChatGPT mirror site, etc.
[^2]: Usually through online services such as feedly or clients such as reeder

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
padding: 20px;
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