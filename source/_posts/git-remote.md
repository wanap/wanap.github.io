---
title: git-remote
date: 2016-09-29 12:35:17
tags:
---
## git远程命令

  git remote [-v]  列出所有远程主机

  git remote add <主机名> <url> 添加一个新的远程 Git 仓库

  git remote rm <主机名> <url> 用于删除远程主机

<!-- more -->

## 从远程主机更新

    git fetch <主机名> <分支名>
然后就可以使用`git merge`命令或`git rebase`命令，在本地分支上合并远程分支  

    #在当前分支上合并orgin主机的master分支
    git merge origin/master 或 git rebase origin/master  

或者直接使用git pull命令，本地分支名不写代表合并到本地当前分支  

    git pull <远程主机名> <远程分支名>:<本地分支名> 

`git fetch` 是将更新取回本地，需要再`git merge`， 而`git pull`是一步到位，取回更新并合并

## 将本地代码推送到远程主机

    git push <远程主机名> <本地分支名>:<远程分支名>
    
创建一个远程分支

    git push <远程主机名> <本地分支名>:<新远程分支名>

删除指定的远程分支
    
    git push origin --delete <远程分支名>
    或者推送一个空的本地分支到远程分支
    git push origin :<远程分支名>

## 如何避免每次输入密码

如果不想在每一次推送时都输入用户名与密码，你可以设置一个 “credential cache”。 最简单的方式就是将其保存在内存中几分钟，可以简单地运行 git config --global credential.helper cache 来设置它。