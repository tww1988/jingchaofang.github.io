前言
----

hexo是一个快速、简洁且高效的博客框架。hexo使用Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。hexo出自台湾大学生SkyArrow之手，是一个基于Node.js的静态博客框架，编译上百篇文字只需要几秒。在已经有Octopress和jekyll的情况下，SkyArrow为什么要自己造轮子呢，可以从他的这篇文章找到答案：[Hexo颯爽登場！](https://zespia.tw/blog/2012/10/11/hexo-debut/)

[hexo作者个人博客](https://zespia.tw/)

[hexo作者github](https://github.com/tommy351)

[hexo官网](https://hexo.io/zh-cn/)

[hexo官方文档](https://hexo.io/zh-cn/docs/)


安装
-----

保证本地已经安装了nodejs和git
```
npm install -g hexo-cli
```
初始化项目
```
hexo init <folder>
cd <folder>
npm install
```
初始化后的目录结构如下
```
.
├── _config.yml   网站配置信息
├── package.json  应用程序信息
├── scaffolds     模板文件夹
├── source        资源文件夹
|   ├── _drafts
|   └── _posts
└── themes        主题文件夹
```

配置
----

可以在 _config.yml中修改大部份的配置。

网站

|参数|描述|
|:----|:----|
|title|网站标题|
|subtitle|网站副标题|
|description|网站描述|
|author|您的名字|
|language|网站使用的语言|
|timezone|网站时区,Hexo 默认使用您电脑的时区。[时区列表](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)。比如说：America/New_York, Japan, 和 UTC 。|

网址

|参数|描述|默认值|
|:---|:----|:---|
|url|网址| |	
|root|网站根目录| |	
|permalink|文章的永久链接格式|:year/:month/:day/:title/|
|permalink_default|永久链接中各部分的默认值| |

网站存放在子目录：如果您的网站存放在子目录中，例如```http://yoursite.com/blog```，则请将您的url设为```http://yoursite.com/blog```并把root设为/blog/。

目录

|参数|描述|默认值|
|:---|:----|:------|
|source_dir|资源文件夹，这个文件夹用来存放内容。|	source|
|public_dir|公共文件夹，这个文件夹用于存放生成的站点文件。|	public|
|tag_dir|标签文件夹|tags|
|archive_dir|归档文件夹|archives|
|category_dir|分类文件夹|categories|
|code_dir|Include code 文件夹|downloads/code|
|i18n_dir|国际化（i18n）文件夹|:lang|
|skip_render|跳过指定文件的渲染，您可使用glob表达式来匹配路径|

文章

|参数|描述|默认值|
|:---|:---|:-----|
|new_post_name|新文章的文件名称|:title.md|
|default_layout|预设布局|post|
|auto_spacing|在中文和英文之间加入空格|false|
|titlecase|把标题转换为title case|false|
|external_link|在新标签中打开链接|true|
|filename_case|把文件名称转换为(1)小写或(2)大写|0|
|render_drafts|显示草稿|false|
|post_asset_folder|启动Asset 文件夹|false|
|relative_link|把链接改为与根目录的相对位址|false|
|future|显示未来的文章|true|
|highlight|代码块的设置||

分类 & 标签

|参数|描述|默认值|
|:---|:---|:---|
|default_category|默认分类|uncategorized|
|category_map|分类别名| |	
|tag_map|标签别名| |	

日期 / 时间格式

Hexo使用[Moment.js](http://momentjs.com/)来解析和显示时间。

|参数|描述|默认值|
|:---|:---|:-----|
|date_format|日期格式|YYYY-MM-DD|
|time_format|时间格式|H:mm:ss|

分页

|参数|描述|默认值|
|:---|:---|:-----|
|per_page|每页显示的文章量 (0 = 关闭分页功能)|10|
|pagination_dir|分页目录|page|

扩展

|参数|描述|
|:---|:---|
|theme|当前主题名称。值为false时禁用主题|
|deploy|部署部分的设置|


指令
----

```
hexo ini [folder] 新建一个网站。如果没有设置 folder ，Hexo 默认在目前的文件夹建立网站。
````

```
hexo new [layout] <title> 新建一篇文章。如果没有设置layout的话，默认使用_config.yml中的default_layout参数代替。如果标题包含空格的话，请使用引号括起来。
```

```
hexo generate 生成静态文件。
```
|选项|描述|
|:---|:----|
|-d, --deploy|文件生成后立即部署网站|
|-w, --watch|监视文件变动|

```
hexo publish [layout] <filename> 发表草稿
```

```
hexo server 启动服务器。默认情况下，访问网址为： http://localhost:4000/
```

|选项|描述|
|:----|:----|
|-p, --port|重设端口|
|-s, --static|只使用静态文件|
|-l, --log|启动日记记录，使用覆盖记录格式|

```
hexo deploy 部署网站
```

|参数|描述|
|:---|:----|
|-g, --generate|部署之前预先生成静态文件|

```
hexo render <file1> [file2] ... 渲染文件
```

|参数|描述|
|:---|:----|
|-o, --output|设置输出路径|

```
hexo migrate <type> 从其他博客系统迁移内容
```
```
hexo clean 清除缓存文件(db.json)和已生成的静态文件(public)
```
```
hexo list <type> 列出网站资料
```
```
hexo version 显示 Hexo 版本
```

指令选项
-------
```
安全模式 hexo --safe 在安全模式下，不会载入插件和脚本。当您在安装新插件遭遇问题时，可以尝试以安全模式重新执行。
```
```
调试模式 hexo --debug 在终端中显示调试信息并记录到debug.log。当您碰到问题时，可以尝试用调试模式重新执行一次，并提交调试信息到GitHub。
```
```
简洁模式 hexo --silent 隐藏终端信息。
```
```
自定义配置文件的路径 hexo --config custom.yml 自定义配置文件的路径，执行后将不再使用_config.yml。
```
```
显示草稿 hexo --draft 显示source/_drafts文件夹中的草稿文章。
```
```
自定义CWD hexo --cwd /path/to/cwd 自定义当前工作目录（Current working directory）的路径。
```

迁移
----

**RSS**

首先，安装hexo-migrator-rss插件，```npm install hexo-migrator-rss --save```
插件安装完成后，执行下列命令，从RSS迁移所有文章。source可以是文件路径或网址。```hexo migrate rss <source>```

**Jekyll**

把```_posts```文件夹内的所有文件复制到```source/_posts```文件夹，并在 ```_config.yml```中修改```new_post_name```参数。

```
new_post_name: :year-:month-:day-:title.md
```

**Octopress**

把Octopress```source/_posts``` 文件夹内的所有文件转移到Hexo的```source/_posts```文件夹，并修改```_config.yml```中的```new_post_name```参数。

```
new_post_name: :year-:month-:day-:title.md
```

**WordPress**

首先，安装hexo-migrator-wordpress插件。

```
npm install hexo-migrator-wordpress --save
````

在WordPress仪表盘中导出数据(“Tools” → “Export” → “WordPress”)（详情参考WP支持页面）。

插件安装完成后，执行下列命令来迁移所有文章。source可以是WordPress导出的文件路径或网址。
```
hexo migrate wordpress <source>
```

**Joomla**

首先，安装 hexo-migrator-joomla 插件。

```
npm install hexo-migrator-joomla --save
```

使用J2XML组件导出Joomla文章。插件安装完成后，执行下列命令来迁移所有文章。source可以是Joomla导出的文件路径或网址。
```
hexo migrate joomla <source>
```

写作
----

你可以执行下列命令来创建一篇新文章。
```
hexo new [layout] <title>
```
您可以在命令中指定文章的布局（layout），默认为post，可以通过修改```_config.yml```中的```default_layout```参数来指定默认布局。


**布局（Layout）**

Hexo有三种默认布局：post、page和draft，它们分别对应不同的路径，而您自定义的其他布局和post相同，都将储存到source/_posts文件夹。

|布局|路径|
|:---|----|
|post|source/_posts|
|page|source|
|draft|source/_drafts|

```
不要处理我的文章：如果你不想你的文章被处理，你可以将Front-Matter中的layout:设为false。
```

**文件名称**

Hexo默认以标题做为文件名称，但您可编辑```new_post_name```参数来改变默认的文件名称，举例来说，设为```:year-:month-:day-:title.md```可让您更方便的通过日期来管理文章。

|变量|描述|
|:---|----|
|:title|标题（小写，空格将会被替换为短杠）|
|:year|建立的年份，比如，2015|
|:month|建立的月份（有前导零），比如，04|
|:i_month|建立的月份（无前导零），比如，4|
|:day|建立的日期（有前导零），比如，07|
|:i_day|建立的日期（无前导零），比如，7|

**草稿**

刚刚提到了Hexo的一种特殊布局：draft，这种布局在建立时会被保存到```source/_drafts```文件夹，您可通过publish命令将草稿移动到```source/_posts```文件夹，该命令的使用方式与new十分类似，您也可在命令中指定layout来指定布局。
```
hexo publish [layout] <title>
```
草稿默认不会显示在页面中，您可在执行时加上--draft参数，或是把render_drafts参数设为true来预览草稿。

**模版（Scaffold）**

在新建文章时，Hexo会根据scaffolds文件夹内相对应的文件来建立文件，例如：
```
hexo new photo "My Gallery"
```
在执行这行指令时，Hexo会尝试在scaffolds 文件夹中寻找photo.md，并根据其内容建立文章，以下是您可以在模版中使用的变量：

|变量|描述|
|:---|----|
|layout|布局|
|title|标题|
|date|文件建立日期|

**Front-matter**

Front-matter是文件最上方以---分隔的区域，用于指定个别文件的变量，举例来说：
```
title: Hello World
date: 2013/7/13 20:46:25
---
```
以下是预先定义的参数，您可在模板中使用这些参数值并加以利用。

|参数|描述|默认值|
|:---|----|------|
|layout|布局||	
|title|标题||	
|date|建立日期|文件建立日期|
|updated|更新日期|文件更新日期|
|comments|开启文章的评论功能|true|
|tags|标签（不适用于分页）||
|categories|分类（不适用于分页）||	
|permalink|覆盖文章网址||

**分类和标签**

只有文章支持分类和标签，您可以在Front-matter中设置。在其他系统中，分类和标签听起来很接近，但是在Hexo中两者有着明显的差别：分类具有顺序性和层次性，也就是说Foo,Bar不等于Bar,Foo；而标签没有顺序和层次。

```
categories:
- Diary
tags:
- PS3
- Games
```

**JSON Front-matter**

除了YAML外，你也可以使用JSON来编写Front-matter，只要将 --- 代换成 ;;; 即可。
```
"title": "Hello World",
"date": "2013/7/13 20:46:25"
;;;
```

标签插件（Tag Plugins）
----------------------

标签插件和Front-matter中的标签不同，它们是用于在文章中快速插入特定内容的插件。

**引用块**

在文章中插入引言，可包含作者、来源和标题。

别号：quote

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}
```

样例：

没有提供参数，则只输出普通的 blockquote
```
{% blockquote %}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.
{% endblockquote %}
```

> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.

引用书上的句子

```
{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}
```

引用 Twitter
```
{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}
```

引用网络上的文章
```
{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}
```

**代码块**

在文章中插入代码。

别名： code

```
{% codeblock [title] [lang:language] [url] [link text] %}
code snippet
{% endcodeblock %}
```

样例:

普通的代码块
```
{% codeblock %}
alert('Hello World!');
{% endcodeblock %}
```

指定语言

```
{% codeblock lang:objc %}
[rectangle setX: 10 y: 10 width: 20 height: 20];
{% endcodeblock %}
```

附加说明
```
{% codeblock Array.map %}
array.map(callback[, thisArg])
{% endcodeblock %}
```

附加说明和网址
```
{% codeblock _.compact http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}
```

**反引号代码块**

另一种形式的代码块，不同的是它使用三个反引号来包裹。

``` [language] [title] [url] [link text] code snippet ```


**Pull Quote**

在文章中插入 Pull quote。
```
{% pullquote [class] %}
content
{% endpullquote %}
```

**jsFiddle**

在文章中嵌入 jsFiddle。
```
{% jsfiddle shorttag [tabs] [skin] [width] [height] %}
```

**Gist**

在文章中嵌入 Gist。

```
{% gist gist_id [filename] %}
```

**iframe**

在文章中插入 iframe。

```
{% iframe url [width] [height] %}
```

**Image**

在文章中插入指定大小的图片。

```
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
```

**Link**

在文章中插入链接，并自动给外部链接添加 target="_blank" 属性。
```
{% link text url [external] [title] %}
```

**Include Code**

插入source文件夹内的代码文件。
```
{% include_code [title] [lang:language] path/to/file %}
```

**Youtube**

在文章中插入 Youtube 视频。

```
{% youtube video_id %}
```

**Vimeo**

在文章中插入 Vimeo 视频。

```
{% vimeo video_id %}
```

**引用文章**

引用其他文章的链接。

```
{% post_path slug %}
{% post_link slug [title] %}
```

**引用资源**

引用文章的资源。
```
{% asset_path slug %}
{% asset_img slug [title] %}
{% asset_link slug [title] %}
```

**Raw**

如果您想在文章中插入Swig标签，可以尝试使用Raw标签，以免发生解析异常。

```
{% raw %}
content
{% endraw %}
```

资源文件夹
----------

资源（Asset）代表source文件夹中除了文章以外的所有文件，例如图片、CSS、JS文件等。比方说，如果你的Hexo项目中只有少量图片，那最简单的方法就是将它们放在source/images文件夹中。然后通过类似于```![](/images/image.jpg)```的方法访问它们。

**文章资源文件夹**

对于那些想要更有规律地提供图片和其他资源以及想要将他们的资源分布在各个文章上的人来说，Hexo也提供了更组织化的方式来管理资源。这个稍微有些复杂但是管理资源非常方便的功能可以通过将```config.yml```文件中的```post_asset_folder```选项设为true来打开。
```
_config.yml
post_asset_folder: true
```
当资源文件管理功能打开后，Hexo将会在你每一次通过```hexo new [layout] <title>```
命令创建新文章时自动创建一个文件夹。这个资源文件夹将会有与这个markdown文件一样的名字。将所有与你的文章有关的资源放在这个关联文件夹中之后，你可以通过相对路径来引用它们，这样你就得到了一个更简单而且方便得多的工作流。

**相对路径引用的标签插件**

通过常规的markdown语法和相对路径来引用图片和其它资源可能会导致它们在存档页或者主页上显示不正确。在Hexo2时代，社区创建了很多插件来解决这个问题。但是，随着Hexo3的发布，许多新的标签插件被加入到了核心代码中。这使得你可以更简单地在文章中引用你的资源。
```
{% asset_path slug %}
{% asset_img slug [title] %}
{% asset_link slug [title] %}
```
比如说：当你打开文章资源文件夹功能后，你把一个example.jpg图片放在了你的资源文件夹中，如果通过使用相对路径的常规markdown语法```![](/example.jpg)``` ，它将不会出现在首页上。（但是它会在文章中按你期待的方式工作）

正确的引用图片方式是使用下列的标签插件而不是markdown ：
```
{% asset_img example.jpg This is an example image %}
```
通过这种方式，图片将会同时出现在文章和主页以及归档页中。

数据文件
--------

有时您可能需要在主题中使用某些资料，而这些资料并不在文章内，并且是需要重复使用的，那么您可以考虑使用Hexo3新增的「数据文件」功能。此功能会载入source/_data内的YAML或JSON文件，如此一来您便能在网站中复用这些文件了。

举例来说，在 source/_data 文件夹中新建 menu.yml 文件：
```
Home: /
Gallery: /gallery/
Archives: /archives/
```
您就能在模板中使用这些资料：
```
{% for link in site.data.menu %}
  <a href="{{ link }}">{{ loop.key }}</a>
{% endfor %}
```




