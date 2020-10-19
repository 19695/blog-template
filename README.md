# blog-template

blog的前台模板



## idea快捷键

### 代码块展开/收起

| 操作         | 快捷键              |
| ------------ | ------------------- |
| expand       | ctrl + 加号         |
| collapse     | ctrl + 减号         |
| expand all   | ctrl + shift + 加号 |
| collapse all | ctrl + shift + 减号 |

 

### 格式化代码

| 操作       | 快捷键          |
| ---------- | --------------- |
| 格式化代码 | CTRL +  ALT + L |



## git撤销commit操作

写完代码后，我们一般这样

git add . //添加所有文件

git commit -m "本功能全部完成"



### 执行完commit后，想撤回commit，怎么办？

```shell
git reset --soft HEAD^
```

这样就成功的撤销了你的commit

注意，仅仅是撤回commit操作，您写的代码仍然保留。

 

说一下个人理解：
HEAD^的意思是上一个版本，也可以写成HEAD~1

如果你进行了2次commit，想都撤回，可以使用HEAD~2

 

### 至于这几个参数：
* --mixed 
  意思是：不删除工作空间改动代码，撤销commit，并且撤销git add . 操作
  这个为默认参数,git reset --mixed HEAD^ 和 git reset HEAD^ 效果是一样的。

* --soft
  不删除工作空间改动代码，撤销commit，不撤销git add . 

* --hard
  删除工作空间改动代码，撤销commit，撤销git add . 

注意完成这个操作后，就恢复到了上一次的commit状态。

 

**顺便说一下，如果commit注释写错了，只是想改一下注释，只需要：**

```shell
git commit --amend
```

此时会进入默认vim编辑器，修改注释完毕后保存就好了。

参考：https://www.cnblogs.com/lfxiao/p/9378763.html



## 插件集成

* [编辑器 MarkDown](https://pandao.github.io/editor.md/)
* [内容排版 typo.css](https://github.com/sofish/typo.css)
* [动画 animate.css](https://daneden.github.io/animate.css) 》https://animate.style/
* [代码高亮 prism](https://github.com/PrismJS/prism) 》 https://prismjs.com/
* [目录生成 Tocbot](https://tscanlin.github.io/tocbot/)
* [二维码生成 qrcode.js](https://davidshimjs.github.io/qrcodejs/)
* [平滑滚动 jquery.scrollTo](https://github.com/flesler/jquery.scrollTo)
* [滚动侦测 waypoints](http://imakewebthings.com/waypoints/)



自己的想法

> 我想加一个 思维导图
>
> 没找到网上现成的，回头再找找，啥时候做再说
>
> 倒是这个可以参考 gitmind https://gitmind.cn/


通过 WebStorm 建templates文件夹，把页面移到下面，ide会自动处理引用的资源文件
一定要勾选search for references
