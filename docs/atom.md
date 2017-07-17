# Atom指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.05.18|

## 在Atom里使用Git-plus插件

1. `ctrl+,` 打开设置界面，在`install`里搜索`Git-plus`并安装
2. 在`Git-plus`的设置里设置`Git Path`
3. 由于`Git-plus`是使用`ssh`连接而非`https`，所以需要确保ssh能够连接Github
4. 设置ssh连接Github请见[这里](https://help.github.com/articles/connecting-to-github-with-ssh/)
5. 在`Git bash`里设置用户名和密码：
``` bash
  git config --global user.name "xxx"
  git config --global user.email "xxx@xxx.com"
```
6. 使用`Git bash`克隆代码库至本地
``` bash
  git clone git@github.com:xxx/xxxx.git
```
7. 使用`Atom`打开对应的代码库，随便修改点什么然后测试`Git-plus`能否正常工作

---
参考链接：

[Atom package git-plus 使用说明](http://deadlion.cn/2016/03/14/Atom-package-git-plus-%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E.html)
