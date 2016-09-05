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
    "fecs_bin": "C:/Users/zy/AppData/Roaming/npm/node_modules/fecs/bin/fecs",
    "node_bin": "D:/Program Files/nodejs/node.exe"
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

点击圆点之后，具体的warning信息会显示在底部的状态栏，如果错误信息太多，状态栏显示不全的话，可以通过Ctrl+~调用SublimeText的Console，里面有更详细的信息。```TODO：windows下sublimetext无法调出更详细信息```

安装使用
--------

npm install fecs -g

fecs || fecs checkout

fecs format

编程规范
--------

[JavaScript编码规范](https://github.com/ecomfe/spec/blob/master/javascript-style-guide.md)

fecs-git-hooks
--------------

在代码提交前检验pre-commit

[fecs-git-hooks](https://github.com/cxtom/fecs-git-hooks)
