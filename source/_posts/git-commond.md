---
title: git-commond
date: 2016-09-28 18:40:57
tags: git
categories: 技术
---
### Git原理：
```javascript

        push <-           -> checkout
Remote------------Repository-------------------workspace
       -> clone    |-------------Index---------|
                       commit <-     add <-
```

<!-- more -->

### 名词解释：

Workspace：工作区

Index / Stage：暂存区

Repository：仓库区（或本地仓库）

Remote：远程仓库


### Git常用命令：

1.如果要上传到GitHub，要先在GitHub上新建一个Repository，然后git clone [url] 到本地

2.添加或删除 文件到 暂存区
     
    # 添加当前目录的所有文件到暂存区    git add .
    # 删除工作区文件，并且将这次删除放入暂存区     git rm [file1] [file2]
    # 停止追踪指定文件，但该文件会保留在工作区     git rm --cached [file]

3.提交 暂存区 到 仓库区，git commit -m [message]

4.上传当前分支到远程仓库，git push

5.branch分支

    # 新建一个分支，但依然停留在当前分支  git branch [branch-name]
    # 切换到指定分支，并更新工作区        git checkout [branch-name]
    # 合并指定分支到当前分支             git merge [branch]
    # 删除分支                          git branch -d [branch-name]

6.其他常用命令

    # 显示有变更的文件             git status
    # 显示当前分支的版本历史        git log
    # 在当前目录新建一个Git代码库   git init

### Git工作流：
    1.使用git init命令新建Git代码库,然后git remote add origin <url>关联到repository
    2.使用git branch dev 新建一个dev分支，切换到dev分支进行开发
    3.git add 添加改动的文件，然后 git commit提交改动
    4.切回到master分支，git merge dev 合并改动到主分支
    5.git push提交到远程仓库


### 新建一个repository后，你可以
##### create a new repository on the command line

    echo "# hexo" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin https://github.com/wanap/hexo.git
    git push -u origin master

##### or push an existing repository from the command line

    git remote add origin https://github.com/wanap/hexo.git
    git push -u origin master
