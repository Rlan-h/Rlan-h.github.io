---
title: 每日一问-post请求可以携带params参数吗？
date: 2023-09-03 17:15:09
tags: 每日一问
categories:
cover:
description:
password:
swiper_index:
swiper_desc:
swiper_cover:
---

post请求可以携带params参数吗?
{% hideBlock 查看答案, #FFCC80, #fff %}
<p style="font-size: 18px; font-weight: 600; color: #E53935">可以</p>

我们使用 `node.js`+`express` 写一个简单的接口服务如下：
将服务挂载到了本地3000端口，定义了一个post请求接口，请求路径为 `/test`，该接口会将调用者传递的`params`和`body`参数返回
```js
const express = require('express')

const app = express()

app.use(express.json())
app.use(express.urlencoded({extended: false}))

app.post('/test', (req, res) => {
  res.send({
    query: req.query,
    body: req.body
  })
})

app.listen(3000, () => {
  console.log('服务已启动')
})
```
接下来我们使用 <a href="https://apifox.com/">Apifox</a> 对该接口进行测试
![](/img/dailyquestion/image.png)
![](/img/dailyquestion/image-1.png)
![](/img/dailyquestion/image-2.png)
可以看到，在post请求前提下，不管是params还是body参数，该接口都可以获取到并将之返回。
{% endhideBlock %}

