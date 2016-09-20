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

服务器
------

Hexo 3.0 把服务器独立成了个别模块，您必须先安装hexo-server才能使用。
```
npm install hexo-server --save
```
安装完成后，输入以下命令以启动服务器，您的网站会在http://localhost:4000下启动。在服务器启动期间，Hexo会监视文件变动并自动更新，您无须重启服务器。
```
hexo server
```
如果您想要更改端口，或是在执行时遇到了EADDRINUSE错误，可以在执行时使用-p选项指定其他端口，如下：
```
hexo server -p 5000
```

**静态模式**

在静态模式下，服务器只处理public文件夹内的文件，而不会处理文件变动，在执行时，您应该先自行执行```hexo generate```，此模式通常用于生产环境（production mode）下。

```
hexo server -s
```

**自定义IP**

服务器默认运行在0.0.0.0，您可以覆盖默认的IP设置，如下：
```
hexo server -i 192.168.1.1
```

**Pow**

Pow是一个Mac系统上的零配置Rack服务器，它也可以作为一个简单易用的静态文件服务器来使用。

安装： ```curl get.pow.cx | sh```

设置：在 ~/.pow文件夹建立链接（symlink）。
```
cd ~/.pow
ln -s /path/to/myapp
```
您的网站将会在http://myapp.dev 下运行，网址根据链接名称而定。

生成文件
--------

使用Hexo生成静态文件快速而且简单。
```
hexo generate
```

**监视文件变动**

Hexo能够监视文件变动并立即重新生成静态文件，在生成时会比对文件的SHA1 checksum，只有变动的文件才会写入。
```
hexo generate --watch
```

**完成后部署**

您可执行下列的其中一个命令，让Hexo在生成完毕后自动部署网站，两个命令的作用是相同的。
```
hexo generate --deploy
hexo deploy --generate
```

部署
-----

Hexo提供了快速方便的一键部署功能，让您只需一条命令就能将网站部署到服务器上。
```
hexo deploy
```
在开始之前，您必须先在_config.yml中修改参数，一个正确的部署配置中至少要有type 参数，例如：
```
deploy:
  type: git
```
您可同时使用多个deployer，Hexo会依照顺序执行每个deployer。
```
deploy:
- type: git
  repo:
- type: heroku
  repo:
```

**Git**

安装hexo-deployer-git。
```
npm install hexo-deployer-git --save
```
修改配置。
```
deploy:
  type: git
  repo: <repository url>
  branch: [branch]
  message: [message]
```

|参数|描述|
|:---|----|
|repo|库（Repository）地址|
|branch|分支名称。如果您使用的是GitHub或GitCafe的话，程序会尝试自动检测。|
|message|自定义提交信息 (默认为 Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }})|

**Heroku**

安装hexo-deployer-heroku。
```
npm install hexo-deployer-heroku --save
```
修改配置。
```
deploy:
  type: heroku
  repo: <repository url>
  message: [message]
```

|参数|描述|
|repo|Heroku库（Repository）地址|
|message|自定提交信息 (默认为 Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }})|


**Rsync**

安装hexo-deployer-rsync。
```
npm install hexo-deployer-rsync --save
```
修改配置。
```
deploy:
  type: rsync
  host: <host>
  user: <user>
  root: <root>
  port: [port]
  delete: [true|false]
  verbose: [true|false]
  ignore_errors: [true|false]
```

|参数|描述|默认值|
|:---|----|------|
|host|远程主机的地址||	
|user|使用者名称||	
|root|远程主机的根目录||	
|port|端口|22|
|delete|删除远程主机上的旧文件|true|
|verbose|显示调试信息|true|
|ignore_errors|忽略错误|false|

**OpenShift**

安装 hexo-deployer-openshift。
```
npm install hexo-deployer-openshift --save
```
修改配置。
```
deploy:
  type: openshift
  repo: <repository url>
  message: [message]
```

|参数|描述|
|:---|----|
|repo|OpenShift 库（Repository）地址|
|message|自定提交信息 (默认为 Site updated: {{ now('YYYY-MM-DD HH:mm:ss') }})|

**FTPSync**

安装hexo-deployer-ftpsync。
```
npm install hexo-deployer-ftpsync --save
```
修改配置。
```
deploy:
  type: ftpsync
  host: <host>
  user: <user>
  pass: <password>
  remote: [remote]
  port: [port]
  ignore: [ignore]
  connections: [connections]
  verbose: [true|false]
```

|参数|描述|默认值|
|:---|----|------|
|host|远程主机的地址||
|user|使用者名称||
|pass|密码||	
|remote|远程主机的根目录|/|
|port|端口|21|
|ignore|忽略的文件或目录||
|connections|使用的连接数|1|
|verbose|显示调试信息|false|

**其他方法**

Hexo生成的所有文件都放在public文件夹中，您可以将它们复制到您喜欢的地方。


永久链接（Permalinks）
---------------------

您可以在_config.yml配置中调整网站的永久链接或者在每篇文章的Front-matter中指定。

**变量**

除了下列变量外，您还可使用Front-matter中的所有属性。

|变量|描述|
|:---|----|
|:year|文章的发表年份（4 位数）|
|:month|文章的发表月份（2 位数）|
|:i_month|文章的发表月份（去掉开头的零）|
|:day|文章的发表日期（2 位数）|
|:i_day|文章的发表日期（去掉开头的零）|
|:title|文件名称|
|:id|文章ID|
|:category|分类。如果文章没有分类，则是 default_category 配置信息。|

您可在permalink_defaults参数下调整永久链接中各变量的默认值：
```
permalink_defaults:
  lang: en
```

**示例**

假设source/_posts文件夹中有个hello-world.md，包含以下内容：
```
title: Hello World
date: 2013-07-14 17:01:34
categories:
- foo
- bar
```

|参数|结果|
|:---|----|
|:year/:month/:day/:title/|2013/07/14/hello-world|
|:year-:month-:day-:title.html|2013-07-14-hello-world.html|
|:category/:title|foo/bar/hello-world|

**多语种支持**

若要建立一个多语种的网站，您可修改```new_post_name```和```permalink```参数，如下：
```
new_post_name: :lang/:title.md
permalink: :lang/:title/
```
当您建立新文章时，文章会被储存到：
```
$ hexo new "Hello World" --lang tw
# => source/_posts/tw/Hello-World.md
```
而网址会是：
```
http://localhost:4000/tw/hello-world/
```

主题
----

创建Hexo主题非常容易，您只要在themes文件夹内，新增一个任意名称的文件夹，并修改_config.yml内的theme设定，即可切换主题。一个主题可能会有以下的结构：
```
.
├── _config.yml
├── languages
├── layout
├── scripts
└── source
```

_config.yml 主题的配置文件。修改时会自动更新，无需重启服务器。

languages 语言文件夹。请参见国际化(i18n)。

layout 布局文件夹。用于存放主题的模板文件，决定了网站内容的呈现方式，Hexo内建Swig模板引擎，您可以另外安装插件来获得EJS、Haml或Jade支持，Hexo根据模板文件的扩展名来决定所使用的模板引擎，例如：
```
layout.ejs   - 使用 EJS
layout.swig  - 使用 Swig
```
您可参考模板以获得更多信息。

scripts 脚本文件夹。在启动时，Hexo 会载入此文件夹内的JavaScript文件，请参见插件以获得更多信息。

source 资源文件夹，除了模板以外的Asset，例如CSS、JavaScript文件等，都应该放在这个文件夹中。文件或文件夹开头名称为_（下划线线）或隐藏的文件会被忽略。

如果文件可以被渲染的话，会经过解析然后储存到public文件夹，否则会直接拷贝到public文件夹。

**发布**

当您完成主题后，可以考虑将它发布到[主题列表](https://hexo.io/themes)，让更多人能够使用您的主题。在发布前建议先进行[主题单元测试](https://github.com/hexojs/hexo-theme-unit-test)，确保每一项功能都能正常使用。发布主题的步骤和更新文档非常类似。

1. Fork hexojs/site
2. 把库（repository）复制到电脑上，并安装所依赖的插件。
```
git clone https://github.com/<username>/site.git
cd site
npm install
```
3. 编辑source/_data/themes.yml，在文件中新增您的主题，例如：
```
- name: landscape
  description: A brand new default theme for Hexo.
  link: https://github.com/hexojs/hexo-theme-landscape
  preview: http://hexo.io/hexo-theme-landscape
  tags:
    - official
    - responsive
    - widget
    - two_column
    - one_column
```
4. 在source/themes/screenshots新增同名的截图档案，图片必须为800x500的PNG文件。
5. 推送（push）分支。
6. 建立一个新的合并申请（pull request）并描述改动。

模版
----

模板决定了网站内容的呈现方式，每个主题至少都应包含一个index模板，以下是各页面相对应的模板名称：

|模板|用途|回调|
|:---|----|----|
|index|首页||
|post|文章|index|
|page|分页|index|
|archive|归档|index|
|category|分类归档|archive|
|tag|标签归档|archive|

**布局（Layout）**

如果页面结构类似，例如两个模板都有页首（Header）和页脚（Footer），您可考虑通过布局让两个模板共享相同的结构。一个布局文件必须要能显示body 变量的内容，如此一来模板的内容才会被显示，举例来说：
```
index.ejs
index
```
```
layout.ejs
<!DOCTYPE html>
<html>
  <body><%- body %></body>
</html>
```
生成：
```
<!DOCTYPE html>
<html>
  <body>index</body>
</html>
```
每个模板都默认使用layout布局，您可在front-matter指定其他布局，或是设为false来关闭布局功能，您甚至可在布局中再使用其他布局来建立嵌套布局。

**局部模版（Partial）**

局部模板让您在不同模板之间共享相同的组件，例如页首（Header）、页脚（Footer）或侧边栏（Sidebar）等，可利用局部模板功能分割为个别文件，让维护更加便利。举例来说：
```
partial/header.ejs
<h1 id="logo"><%= config.title %></h1>
```
```
index.ejs
<%- partial('partial/header') %>
<div id="content">Home page</div>
```
生成：
```
<h1 id="logo">My Site</h1>
<div id="content">Home page</div>
```

局部变量：您可以在局部模板中指定局部变量并使用。
```
partial/header.ejs
<h1 id="logo"><%= title></h1>
```
```
index.ejs
<%- partial('partial/header', {title: 'Hello World'}) %>
<div id="content">Home page</div>
```
生成：
```
<h1 id="logo">Hello World</h1>
<div id="content">Home page</div>
```

**优化**

如果您的主题太过于复杂，或是需要生成的文件量太过于庞大，可能会大幅降低性能，除了简化主题外，您可以考虑Hexo 2.7新增的局部缓存（Fragment Caching）功能。

本功能借鉴于Ruby on Rails，它储存局部内容，下次便能直接使用缓存内容，可以减少文件夹查询并使生成速度更快。

它可用于页首、页脚、侧边栏等文件不常变动的位置，举例来说：
```
<%- fragment_cache('header', function(){
  return '<header></header>';
});
```
如果您使用局部模板的话，可以更简单：
```
<%- partial('header', {}, {cache: true});
```
但是，如果您开启了relative_link参数的话，请勿使用局部缓存功能，因为相对链接在每个页面可能不同。

变量
-----

**全局变量**

|变量|描述|
|:---|----|
|site|网站变量|
|page|针对该页面的内容以及 front-matter 所设定的变量。|
|config|网站配置|
|theme|主题配置。继承自网站配置。|
|_ (单下划线)|[Lodash](https://lodash.com/)函数库|
|path|当前页面的路径（不含根路径）|
|url|当前页面的完整网址|
|env|环境变量|

**网站变量**

|变量|描述|
|:---|----|
|site.posts|所有文章|
|site.pages|所有分页|
|site.categories|所有分类|
|site.tags|所有标签|

**页面变量**

页面（page）

|变量|描述|
|:---|----|
|page.title|页面标题|
|page.date|页面建立日期（Moment.js 对象）|
|page.updated|页面更新日期（Moment.js 对象）|
|page.comments|留言是否开启|
|page.layout|布局名称|
|page.content|页面的完整内容|
|page.excerpt|页面摘要|
|page.more|除了页面摘要的其余内容|
|page.source|页面原始路径|
|page.full_source|页面的完整原始路径|
|page.path|页面网址（不含根路径）。我们通常在主题中使用 url_for(page.path)。|
|page.permalink|页面的完整网址|
|page.prev|上一个页面。如果此为第一个页面则为 null。|
|page.next|下一个页面。如果此为最后一个页面则为 null。|
|page.raw|文章的原始内容|
|page.photos|文章的照片（用于相簿）|
|page.link|文章的外部链接（用于链接文章）|

文章 (post):和page布局类似，但是添加了下列变量。

|Variable|Description|
|:-------|-----------|
|page.published|如果该文章已发布则为True|
|page.categories|该文章的所有分类|
|page.tags|该文章的所有标签|

**首页（index）**

|变量|描述|
|:---|----|
|page.per_page|每页显示的文章数量|
|page.total|总文章数|
|page.current|目前页数|
|page.current_url|目前分页的网址|
|page.posts|本页文章|
|page.prev|上一页的页数。如果此页是第一页的话则为 0。|
|page.prev_link|上一页的网址。如果此页是第一页的话则为 ''。|
|page.next|下一页的页数。如果此页是最后一页的话则为 0。|
|page.next_link|下一页的网址。如果此页是最后一页的话则为 ''。|
|page.path|当前页面的路径（不含根目录）。我们通常在主题中使用 url_for(page.path)。|

归档 (archive)：与index布局相同，但新增以下变量。

|变量|描述|
|:---|----|
|page.archive|等于 true|
|page.year|年份归档 (4位)|
|page.month|月份归档 (没有前导零的2位数)|

分类 (category)：与index布局相同，但新增以下变量。

|变量|描述|
|:---|----|
|page.category|分类名称|

标签 (tag)：与index布局相同，但新增以下变量。

|变量|描述|
|:---|----|
|page.tag|标签名称|


辅助函数（Helpers）
-----------------

辅助函数帮助您在模版中快速插入内容。辅助函数不能在源文件中使用。

**网址**

url_for：在路径前加上根路径，从 Hexo 2.7 开始您应该使用此函数而不是 config.root + path。
```
<%- url_for(path) %>
```
relative_url：取得与from相对的to路径。
```
<%- relative_url(from, to) %>
```

gravatar：插入Gravatar图片。

如果你不指定options参数，将会应用默认参数。否则，你可以将其设置为一个数字，这个数字将会作为Gravatar的大小参数。最后，如果你设置它一个对象，它将会被转换为Gravatar的一个查询字符串参数。
````
<%- gravatar(email, [options]);
```
示例：
```
<%- gravatar('a@abc.com') %>
// http://www.gravatar.com/avatar/b9b00e66c6b8a70f88c73cb6bdb06787
<%- gravatar('a@abc.com', 40) %>
// http://www.gravatar.com/avatar/b9b00e66c6b8a70f88c73cb6bdb06787?s=40
<%- gravatar('a@abc.com' {s: 40, d: 'http://example.com/image.png'}) %>
// http://www.gravatar.com/avatar/b9b00e66c6b8a70f88c73cb6bdb06787?s=40&d=http%3A%2F%2Fexample.com%2Fimage.png
```

**HTML标签**

css：载入CSS文件。path可以是数组或字符串，如果path开头不是/或任何协议，则会自动加上根路径；如果后面没有加上.css扩展名的话，也会自动加上。
```
<%- css(path, ...) %>
```
示例：
```
<%- css('style.css') %>
// <link rel="stylesheet" href="/style.css" type="text/css">
<%- css(['style.css', 'screen.css']) %>
// <link rel="stylesheet" href="/style.css" type="text/css">
// <link rel="stylesheet" href="/screen.css" type="text/css">
```

js：载入JavaScript文件。path可以是数组或字符串，如果path开头不是/或任何协议，则会自动加上根路径；如果后面没有加上.js扩展名的话，也会自动加上。
```
<%- js(path, ...) %>
```
示例：
```
<%- js('script.js') %>
// <script type="text/javascript" src="/script.js"></script>
<%- js(['script.js', 'gallery.js']) %>
// <script type="text/javascript" src="/script.js"></script>
// <script type="text/javascript" src="/gallery.js"></script>
```

link_to：插入链接。
```
<%- link_to(path, [text], [options]) %>
```
|参数|描述|默认值|
|:---|----|------|
|external|在新视窗打开链接|false|
|class|Class名称||	
|id|ID||	

示例：
```
<%- link_to('http://www.google.com') %>
// <a href="http://www.google.com" title="http://www.google.com">http://www.google.com</a>
<%- link_to('http://www.google.com', 'Google') %>
// <a href="http://www.google.com" title="Google">Google</a>
<%- link_to('http://www.google.com', 'Google', {external: true}) %>
// <a href="http://www.google.com" title="Google" target="_blank" rel="external">Google</a>
```

mail_to：插入电子邮箱链接。
```
<%- mail_to(path, [text], [options]) %>
```
|参数|描述|
|:---|----|
|class|Class名称|
|id|ID|
|subject|邮件主题|
|cc|抄送（CC）|
|bcc|密送（BCC）|
|body|邮件内容|

示例：
```
<%- mail_to('a@abc.com') %>
// <a href="mailto:a@abc.com" title="a@abc.com">a@abc.com</a>
<%- mail_to('a@abc.com', 'Email') %>
// <a href="mailto:a@abc.com" title="Email">Email</a>
```

image_tag：插入图片。
```
<%- image_tag(path, [options]) %>
```
|参数|描述|
|alt|图片的替代文字|
|class|Class名称|
|id|ID|
|width|图片宽度|
|height|图片高度|

favicon_tag：插入 favicon。
```
<%- favicon_tag(path) %>
```

feed_tag：插入 feed 链接。
```
<%- feed_tag(path, [options]) %>
```
|参数|描述|默认值|
|title|Feed 标题||	
|type|Feed 类型|atom|

**条件函数**

is_current：检查path是否符合目前页面的网址。开启strict选项启用严格比对。
```
<%- is_current(path, [strict]) %>
```
is_home 检查目前是否为首页。
```
<%- is_home() %>
```
is_post 检查目前是否为文章。
```
<%- is_post() %>
```
is_archive 检查目前是否为存档页面。
```
<%- is_archive() %>
```
is_year 检查目前是否为年度归档页面。
```
<%- is_year() %>
```
is_month 检查目前是否为月度归档页面。
```
<%- is_month() %>
```
is_category 检查目前是否为分类归档页面。

如果给定一个字符串作为参数，将会检查目前是否为指定分类。
```
<%- is_category() %>
<%- is_category('hobby') %>
```
is_tag 检查目前是否为标签归档页面。

如果给定一个字符串作为参数，将会检查目前是否为指定标签。
```
<%- is_tag() %>
<%- is_tag('hobby') %>
```

**字符串处理**

trim 清除字符串开头和结尾的空格。
```
<%- trim(string) %>
```
strip_html 清除字符串中的HTML标签。
```
<%- strip_html(string) %>
```
示例：
```
<%- strip_html('It's not <b>important</b> anymore!') %>
// It's not important anymore!
```
titlecase 把字符串转换为正确的 Title case。
```
<%- titlecase(string) %>
```
示例：
```
<%- titlecase('this is an apple') %>
# This is an Apple
```
markdown 使用Markdown解析字符串。
```
<%- markdown(str) %>
```
示例：
```
<%- markdown('make me **strong**') %>
// make me <strong>strong</strong>
```
render 解析字符串。
```
<%- render(str, engine, [options]) %>
```
word_wrap 使每行的字符串长度不超过length。length预设为80。
```
<%- word_wrap(str, [length]) %>
```
示例：
```
<%- word_wrap('Once upon a time', 8) %>
// Once upon\n a time
```
truncate 移除超过 length 长度的字符串。
```
<%- truncate(text, length) %>
```
示例：
```
<%- truncate('Once upon a time in a world far far away', {length: 17}) %>
// Once upon a ti...
<%- truncate('Once upon a time in a world far far away', {length: 17, separator: ' '}) %>
// Once upon a...
<%- truncate('And they found that many people were sleeping better.', {length: 25, omission: '... (continued)'}) %>
// And they f... (continued)
```

**模板**

partial 载入其他模板文件，您可在locals设定区域变量。
```
<%- partial(layout, [locals], [options]) %>
```
|参数|描述|默认值|
|:---|----|------|
|cache|缓存（使用Fragment cache）|false|
|only|限制局部变量。在模板中只能使用locals中设定的变量。|false|

fragment_cache 局部缓存。它储存局部内容，下次使用时就能直接使用缓存。
```
<%- fragment_cache(id, fn);
```
示例：
```
<%- fragment_cache('header', function(){
  return '<header></header>';
}) %>
```

**日期与时间**

date 插入格式化的日期。date可以是UNIX时间、ISO字符串、Date对象或Moment.js对象。format默认为date_format配置信息。
```
<%- date(date, [format]) %>
```
示例：
```
<%- date(Date.now()) %>
// 2013-01-01
<%- date(Date.now(), 'YYYY/M/D') %>
// Jan 1 2013
```

date_xml 插入XML格式的日期。date可以是UNIX时间、ISO 字符串、Date对象或Moment.js对象。
```
<%- date_xml(date) %>
```
示例：
```
<%- date_xml(Date.now()) %>
// 2013-01-01T00:00:00.000Z
```

time 插入格式化的时间。date可以是UNIX时间、ISO字符串、Date对象或Moment.js对象。format默认为time_format配置信息。
```
<%- time(date, [format]) %>
```
示例：
```
<%- time(Date.now()) %>
// 13:05:12
<%- time(Date.now(), 'h:mm:ss a') %>
// 1:05:12 pm
```

```full_date```插入格式化的日期和时间。date可以是UNIX 时间、ISO字符串、Date对象或Moment.js对象。format默认为```date_format + time_format```。
```
<%- full_date(date, [format]) %>
```
示例：
```
<%- full_date(new Date()) %>
// Jan 1, 2013 0:00:00
<%- full_date(new Date(), 'dddd, MMMM Do YYYY, h:mm:ss a') %>
// Tuesday, January 1st 2013, 12:00:00 am
```
moment [Moment.js](http://momentjs.com/)函数库。

**列表**

list_categories 插入分类列表。
```
<%- list_categories([options]) %>
```

|参数|描述|默认值|
|:---|----|------|
|orderby|分类排列方式|name|
|order|分类排列顺序。1, asc 升序；-1, desc 降序。|1|
|show_count|显示每个分类的文章总数|true|
|style|分类列表的显示方式。使用list以无序列表（unordered list）方式显示。|list|
|separator|分类间的分隔符号。只有在style不是list时有用。|	,|
|depth|要显示的分类层级。0显示所有层级的分类；-1和0很类似，但是显示不分层级；1只显示第一层的分类。|0|
|class|分类列表的class名称。|category|
|transform|改变分类名称显示方法的函数||

