Fecs
-----

[wiki](https://github.com/ecomfe/fecs/wiki)

编辑器插件
----------

[SublimeText&WebStorm插件](https://github.com/leeight/Baidu-FE-Code-Style)

window下的配置文件

```
{
  "env": {
    "fecs_bin": "C:\\Users\\zy\\AppData\\Roaming\\npm\\node_modules\\fecs\\bin\\fecs",
    "node_bin": "D:\\Program Files\\nodejs\\node.exe"
  }
}
```

mac下的配置文件
```
{
  "env": {
    "fecs_bin": "/usr/local/bin/fecs",
    "node_bin": "/usr/local/bin/node"
  }
}

```

点击圆点之后，具体的warning信息会显示在底部的状态栏，如果错误信息太多，状态栏显示不全的话，可以通过Ctrl+~调用SublimeText的Console，里面有更详细的信息。```TODO：windows下sublimetext无法调出更详细信息，sublimetext使用该插件经常报错```

安装使用
--------

```
npm install fecs -g
```

```
fecs || fecs check
```

使用eslint对当前目录下所有JavaScript代码进行检测。使用csshint对当前目录下所有CSS代码进行检测。使用htmlcs对当前目录下所有HTML代码进行检测。

```
fecs dir1 dir2 匹配多个目录
```

```
fecs dir1 --type=js 只检查js文件
```

```
fecs format 默认发布到ouput新目录

fecs format --replace 覆盖当前文件
```

```
fecs --reporter=baidu 显示为百度中文规范提示，默认显示英文提示
```

[Fecs 命令](https://github.com/ecomfe/fecs/wiki/CLI)

忽略规则
-------

使用.fecsignore文件配置，但是fecs check file 优先级最高会忽略该规则文件。

使用指令忽略具体文件
```
fecs --ignore='test.js'
```

编程规范
--------

[JavaScript编码规范](https://github.com/ecomfe/spec/blob/master/javascript-style-guide.md)

[Css编码规范](https://github.com/ecomfe/spec/blob/master/css-style-guide.md)

[Html编码规范](https://github.com/ecomfe/spec/blob/master/html-style-guide.md)

[Eslint默认规则](http://eslint.org/docs/rules/)

[Eslint的Fecs配置规则](https://github.com/ecomfe/fecs/blob/master/lib/js/eslint.yml)

[fixmyjs默认规则](http://jshint.com/docs/options/)

[fixmyjs的Fecs配置规则](https://github.com/ecomfe/fecs/blob/master/lib/js/jshint.yml)

由于修复后的代码生成使用escodegen，它将忽略源码中的空行，因此格式化后的代码将会缺少原有的空行(相关讨论)，目前的解决方案是使用 --safe=high 放弃更多的修复，但保留源码空行。激进用户可以尝试使用--safe=low 来作更多的修复。

[Csslint默认规则](https://github.com/ecomfe/node-csshint/blob/master/lib/config.js)

[Csslint的Fecs配置规则](https://github.com/ecomfe/fecs/blob/master/lib/css/csshint.yml)

[Htmlcs默认规则](https://github.com/ecomfe/htmlcs/blob/master/lib/default/htmlcsrc)

[Htmlcs的Fecs配置规则](https://github.com/ecomfe/fecs/blob/master/lib/html/htmlcs.yml)

由于部分规则ESLint默认未实现（如缩进的indent和单var定义多个变量的disallow-multi-var）或实现得太粗旷或有Bug（如检查JSDoc3注释的valid-jsdoc）等，我们在FECS作了修改版，此类规则在配置文件中的表现是多了fecs-前缀。

检查结果对应的规则名称，可以在执行时使用rule 参数：fecs --rule

配置文件
--------

.fecsrc文件，配置项将会覆盖FECS的默认值


fecs-git-hooks
--------------

pre-commit在代码提交前检验

[fecs-git-hooks](https://github.com/cxtom/fecs-git-hooks)

```
npm install fecs-git-hooks -g
```

问题：window下无法找到.git目录
解决：用方案封装好的shell脚本进行安装
```
sh install.sh
```

FAQ
----

[FAQ](https://github.com/ecomfe/fecs/wiki/FAQ)

[Fecs自有规则](https://github.com/ecomfe/fecs/wiki/FECSRules)

[HowToFix](https://github.com/ecomfe/fecs/wiki/HowToFix)
