---
layout: page
title: About
description: 世界以痛吻我，我要报之以歌。
keywords: beansjie
comments: true
menu: 关于
permalink: /about/
---

从纷繁多复杂的社会现象中认识事物的本质。

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
