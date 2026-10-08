这里理论上来讲应该是主页？
不知道Github如何处理多个符合主页命名标准的页面之间的优先级。

下面应该是一些神秘的 Jekyll 语法，可以把文章目录列出来：

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}