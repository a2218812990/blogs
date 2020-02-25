# 关于eslint插件

> eslint插件能够更好的帮我们规范的代码的编写，提高编程的效率。在实际开发的过程中，我们发现eslint这个插件似乎不太好用。

从vscode软件商店中，我们看到它更新的频率太快了。猜想应该是出现的问题不少，官方也一直在不停的修复。

很多人发现，安装最新版的eslint后突然失效了，代码写不成了。经过亲自测试，用一下方法应该能解决最新版安装不起作用的问题。

第一步，先打开vscode,点击设置.
第二步，右上角有个图标打开设置（json），点击进入settings.json文件中。
第三步，输入如下代码

```js
"eslint.validate": [

        "javascript",
    
        "javascriptreact",
    
        {
    
          "language": "vue",
    
          "autoFix": true
    
        },
    
        "vue"
    
      ],
    
      "eslint.autoFixOnSave": true,
      "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
      }
```

最后重启vscode,你会发现eslint已经生效了。
