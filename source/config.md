---
title: 基本配置
type: docs
permalink: config/
date: 2020-04-24 10:30:08
---

请使用 Notepad++，VS Code，Vim 等编辑器打开主题配置文件。对于 Windows 用户，**不建议** 使用自带记事本打开配置文件，因为可能会带来难以预测的编码错误。

## CDN

主题所采用的CDN。

通常使用 CDN 加载静态文件能使站点访问更快且更稳定，主题默认开启 CDN 加载主要 CSS 文件 `style.css`。如果你对样式进行了一定程度的修改，请关闭 CDN 或者更改为对应 CDN 配置，**否则修改不会生效**！

部分第三方服务也需要使用 CDN 加载资源，详见 [第三方服务](/third-party/) 及 [拓展插件](/expand/)。

## Head

生成 HTML 的头部信息 `<head>`。

### favicon

站点图标。

```yaml
favicon: /favicon.ico
```

默认为网页目录下的 `/favicon.ico`（根据 Hexo 生成规则也就是 `source/favicon.ico`），可以替换为其他路径，如：

```yaml
favicon: https://cdn.jsdelivr.net/npm/chrdnx@1.0.5/icon/favicon-32-transparent.png
```

这样便无需再将图标下载至站点目录中。

### opengraph

社交链接分享协议，开启后在国外社交平台（Twitter、Facebook、Telegram 等）粘贴文章链接便能自动生成分享卡片。

```yaml
opengraph: 
  enable: true
  tc_type: summary_large_image
```

其中 `tc_type` 即 Twitter Card Type，可参照 Twitter [官方文档](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/abouts-cards) 了解详情。

### custom_text

可以在此处随意添加信息，所有内容会被追加到 `<head>` 内，例如搜索引擎所有权验证等。

```yaml
custom_head: 
  - '<meta name="xxxx-site-verification" content="xxxxxxxxxxxxxxxx" />'
  - '<meta name="xxxx-site-verification" content="xxxxxxxxxxxxxxxx" />'
  ...
```

## Cover

封面配置，默认显示在除了文章页的任何页面顶部。

### sitename

显示在封面的标题，如已设置 `logo` 则不展示 `sitename` 。如果此处留空将自动默认为站点配置文件的 `title`。

```yaml
sitename: [ title ]
```

### logo

站点徽标（注意此项与 `favicon` 不同），如已设置 `logo` 则不展示 `sitename` ，展示在封面。如果两项均设置将优先展示 `logo`。

```yaml
logo: [ url of your logo ]
```

### description

一句话介绍/个性签名，展示在 `sitename`/`logo` 下方。

```yaml
description: Hi, nice to meet you!
```

### menu

位于封面最后的按钮菜单，通常用于站内导航。

```yaml
menu: 
  - name: 首页
    url: /
  - name: 标签
    url: /tags/
  - name: 归档
    url: /archives/
  - name: 友链
    url: /friends/
  - name: RSS
    url: /atom.xml
```

每个按钮包含两个参数：`name` 和 `url`。前者定义按钮的显示文字，后者定义点击按钮所跳转的链接。

>   通常情况下，每个按钮显示文字 4 个字宽（每个中文占两个字宽），5 个按钮已是上限。若按钮过多可能导致在小屏设备上难以操作。

## Style

用于控制站点自定义样式。再次提醒：如需自定义样式，请关闭默认 CDN 或更改对应 CDN 配置！

### box

设置内容板块最大宽度、logo 最大宽度及友链盒子最大宽度。

```yaml
box: 
  max_width: 800px		# 内容板块最大宽度
  sp_width: 1540px		# 当屏幕宽度大于 2200px 时替代 max_width
  max_width_logo: 600px	# logo 最大宽度
  link_item: 16rem		# 友链盒子最大宽度
```

>   根据谷歌发布的排版指南，不建议主要内容板块每行超过 80 个字宽（也就是 40 个汉字），否则过宽的内容可能会导致读者阅读负担上升。所以上述内容板块最大宽度也不应设置过大。

### color

颜色样式设置，从上往下依次是：主颜色、链接颜色、链接选中时颜色、标题颜色、背景颜色、卡片背景颜色、字体颜色、代码块背景颜色、分类标记背景颜色、标签标记背景颜色、网站页脚文字颜色、网站页脚链接颜色。

```yaml
color: 
  main_color: '#ffb90f'			# 主颜色
  link_color: '#ffb90f'			# 链接颜色
  link_color_hover: '#eb5757'	# 链接选中时颜色
  title: '#50596c'				# 标题颜色
  background: '#f4f4f4'			# 背景颜色
  card_color: '#fff'			# 卡片背景颜色
  font_color: '#444'			# 字体颜色
  codeblock: '#fffbf3'			# 代码块背景颜色
  categories_block: '#c2c2c2'	# 分类标记背景颜色
  tags_block: '#f4f4f4'			# 标签标记背景颜色
  footer_text: '#999'			# 网站页脚文字颜色
  footer_link: '#6c6c6c'		# 网站页脚链接颜色
```

![](/assets/img/style-color-space.png)

![](/assets/img/style-color-button-footer.png)

### radius

设置卡片及按钮的边框圆角半径。

```yaml
radius: 
  main: 5px
  button: 5px
```

![](/assets/img/style-radius.png)

### space

基准间距，防止板块相距过密。

```yaml
space: 
  main: 3.5rem
  s_main: 2rem	# 当屏幕宽度小于 700px 时候启用
  sm_main: 1rem	# 当屏幕宽度小于 450px 时候启用
```

![](/assets/img/style-color-space.png)

### font

字体设置。

```yaml
font: 
  base_fontsize: 16px
  line_height: '1.8' 
```

## Meta

设置譬如默认文章标题、日期格式、文章尾部版权声明、自定义 footer 等信息格式。

### title

默认文章标题。当一篇文章不含标题时自动展示此标题顶替。

```yaml
# 默认文章标题，若文章无标题则展示此标题
title: 
```

### author

默认作者，现暂主要用于 copyright 声明。日后会考虑添加展示文章作者的功能，方便多用户站点。

```yaml
# 默认文章作者（可在front-matter中覆盖）
author:
  name: ChrAlpha
  url: https://chralpha.com
```

此设置可在文章 `front-matter` 中覆盖。

### date

文章创建日期，通常展示在首页文章摘要下方与文章页标题下方（可在 `layout` 处调整，详见下文）。

```yaml
# 文章创建日期
date:
  title: ''				# 展示在发布日期前的描述
  format: 'YYYY-MM-DD'	# 日期格式 http://momentjs.com/docs/
```

### updated

文章更新日期，通常展示在文章板块最下方。

```yaml
# 文章更新日期
updated:
  title: '最后更新于：'	# 展示在更新日期前的描述
  format: 'YYYY-MM-DD'	# 日期格式 http://momentjs.com/docs/
```

### copyright

版权声明，若开启将默认文章板块最下方。

```yaml
copyright: 
  enable: true
  
  # 永久链接前的描述
  permalink: '本文链接：'
  
  # 在作者声明和永久链接之间，可以多行，支持 markdown
  custom_text:
    - '文章默认使用 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh) 协议进行许可，使用时请注意遵守协议。'
```

可在 `front-matter` 中关闭指定页面的 copyright 组件展示。

```yaml
copyright: false
```

### footer（网站页脚）

网站页脚内容，展示在网页最下方 footer。可以自定义内容，如用于备案号声明等，使用 markdown 标记语言。

```yaml
# 网站页脚，支持 markdown
footer:
  - 'Copyright © 2020 '
  - 'Powered by [Hexo](https://hexo.io) | Theme - [Cards](https://github.com/ChrAlpha/hexo-theme-cards)'
```

如果你喜欢「Cards」，非常欢迎在 footer 中保留主题信息，让更多人了解本主题。感谢支持！

## Layout

用于控制元素展示与否。由于排版固定，所以以下内容 **仅控制展示与否、不控制展示顺序**。

```yaml
layout: 

  # 首页/归档
  # title/excerpt/thumbnail/date/updated/categories/tags
  meta: 
    - excerpt
    - thumbnail
    - date
    - categories
    # - tags

  # 文章页
  post: 
    header:
      - thumbnail
      - date
      - categories
    footer: 
      - copyright
      - updated
      - tags
```

![](/assets/img/post-list-meta.png)

![](/assets/img/post-header-footer.png)

我们认为文章的标题、内容等元素是必要的，所以没有提供选项，而是 **默认开启**。