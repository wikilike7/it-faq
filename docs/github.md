# Github指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.04.25|
|0.02|Shichao Wang|2017.08.01|
|0.03|Shichao Wang|2017.10.24|

## 添加一个已有的工作目录至Github

1.在Github上新建一个仓库，但是不要初始化README，License和.gitignore文件

2.打开`Git bash`(其他也可以)

3.更改目录至需要上传的目录(如`cd d/workspace`)

4.`git init`

5.`git add -A`

6.`git commit -m "initial commit"`

7.回到Github网站，拷贝仓库的地址,可以见截图位置：

![11](./images/github-reposity-url.jpg)

8.再回到命令行，输入以下命令：

``` bash
    git remote add origin 拷贝的仓库地址
    git remote -v
    git push -u origin master

```

## 更改远程仓库的地址

1.`git remote -v`, 获取当前的地址是什么

2.`git remote set-url origin <new url>`

## Host Key verification failed

1.`ssh-keygen -t rsa github.com >> ~/.ssh/know_hosts`

## fatal: refusing to merge unrelated histories

1. [stackoverflow上的解决方法](https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories)

## Git常见命令

1. 分支
    1. `git checkout -b <branch-name>`  //Creating branch and switch
    2. `git branch <branch-name>`  //creating branch

2. Basic setting
    ```
    git config --global user.name "xxx"
    git config --global user.email "yyy"
    git config --global core.editor code  //code means Visual Studio Code
    ```

3. Basic knowledge
    1. workspace
        1. the folder store your code, like "c:\workspace"
   
    2. stage
        1. when you use `git add .`, it means files added to stage

    3. repository
        1. after use `git commit -m "xxx"` the files added to local repository to push

    4. remote
        1. after use `git push origin master` files upload to remote repository




## What is pull
is actually equivalent to the following two steps:
```
git fetch
git merge origin/master
```

## [Github常见错误](http://www.jianshu.com/p/feb3a14c24ef)
