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

# computed和watch以及methods有什么区别？

## 1.计算属性和watch的区别

计算属性是计算属性，侦听器watch是侦听器watch。

计算属性顾名思义就是通过其他变量计算得来的另一个属性，fullName在它所依赖firstName，lastName这两个变量变化时重新计算自己的值。

另外，**计算属性具有缓存**。计算属性是基于它们的依赖进行缓存的。计算属性只有在它的相关依赖发生改变时才会重新求值。这就意味着只要 lastName和firstName都没有发生改变，多次访问 fullName计算属性会立即返回之前的计算结果，而不必再次执行函数。

而侦听器watch是侦听一个特定的值，当该值变化时执行特定的函数。例如分页组件中，我们可以监听当前页码，当页码变化时执行对应的获取数据的函数。