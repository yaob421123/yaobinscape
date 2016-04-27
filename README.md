# yaobinscape

这是一个简洁的主题，基于 landscape 主题更改 [Hexo].

- [yaobinscape](http://yaob421123.github.io/)

## Installation

### Install

``` bash
$ git clone https://github.com/yaob421123/yaobinscape.git themes/yaobinscape
```

**Landscape requires Hexo 2.4 and above.**

### Enable

Modify `theme` setting in `_config.yml` to `yaobinscape`.

### Update

``` bash
cd themes/yaobinscape
git pull
```

## Configuration

``` yml
# Header
menu:
  Home: /
  Archives: /archives
rss: /atom.xml

# Content
excerpt_link: Read More
fancybox: true

# Sidebar
sidebar: right
widgets:
- category
- tag
- tagcloud
- archives
- recent_posts

# Miscellaneous
google_analytics:
favicon: /favicon.png
twitter:
google_plus:
```

# 注意翻页
因为本主题没有做翻页的功能。所以在博客跟目录 `_config.yml` 文件中要设置 `per_page: 0` ，设置为 `0` 显示所有文章
``` bash
per_page: 0
pagination_dir: page
```

# 多说评论
注册你自己的多说账号 duoshuo 替换你在根目录`_config.yml` 中的 duoshuo `short_name` 的值，没有在里面设置
``` bash
duoshuo_shortname : short_name
```

然后再`themes\landscape\layout_partial\article.ejs` 添加一下代码

``` bash
 <% if (!index && post.comments && config.duoshuo_shortname){ %>
  <section id="comments">
   <!-- 多说评论框 start -->
<div id="ds-thread" class="ds-thread" data-thread-key="<%= post.path %>" data-title="<%= post.title %>" data-url="<%= post.permalink %>"></div>
<!-- 多说评论框 end -->
<!-- 多说公共JS代码 start (一个网页只需插入一次) -->
<script type="text/javascript">
var duoshuoQuery = {short_name:"datoublog"};
	(function() {
		var ds = document.createElement('script');
		ds.type = 'text/javascript';ds.async = true;
		ds.src = (document.location.protocol == 'https:' ? 'https:' : 'http:') + '//static.duoshuo.com/embed.js';
		ds.charset = 'UTF-8';
		(document.getElementsByTagName('head')[0] 
		 || document.getElementsByTagName('body')[0]).appendChild(ds);
	})();
	</script>
<!-- 多说公共JS代码 end -->
  </section>
  <% } %>
```
