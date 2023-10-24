---
title: 关于JavaScript中console的内置方法
date: 2023-09-11 00:15:41
tags:
categories:
cover:
description:
password:
swiper_index:
swiper_desc:
swiper_cover:
---

## 打印调试信息

**console.debug()**

{% gallery %}
![](https://im.gurl.eu.org/file/50117c7a5ac73a8d8ce94.png)
![](https://im.gurl.eu.org/file/89063d7e524f14fe5586d.png)
{% endgallery %}
浏览器日志级别：
- 详细(Verbose)
- 信息(Info)
- 警告(Warnings)
- 错误(Errors)
通常浏览器控制台日志级别默认为默认级别(未勾选详细信息)，把浏览器日志级别勾选上详细(Verbose)，即可在控制台看见调试信息

## 打印消息

### 普通消息

**console.log()**

{% gallery %}
![](https://im.gurl.eu.org/file/2a6a64e856ed609078a59.png)
{% endgallery %}

**console.info()**
{% gallery %}
![看不见info信息](https://im.gurl.eu.org/file/bb9a79aae65efbacf9062.png)
![日志级别勾选信息之后可以可见](https://im.gurl.eu.org/file/dd1aba62dc43a04f41ff2.png)
{% endgallery %}
不同浏览器的info样式不一样，可自行尝试

**console.table()**