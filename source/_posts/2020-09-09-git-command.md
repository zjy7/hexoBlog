---
title: git command
date: 2020-09-09 16:53:53
tags:
categories:
---

git init 初始化仓库

git init --bare 初始化一个裸仓库

git branch 查看本地分支

git branch -a 查看全部分支

git remote 远程仓库管理 add show rename rm

git add file 跟踪文件

git checkout -- file （已跟踪）撤销更改

git branch 创建分支

git checkout 切换分支

git checkout -b 创建并切换分支

git status 检测当前状态

git reset 取消暂存文件

git fetch 抓取远程数据

git pull 抓取远程数据并合并

git push 将本地数据推送到远程仓库

git merge 合并分支

git push origin :branch-name 删除远端分支

-----------

恢复上一次提交的状态(commit 之后回退)
通过SHA值可以回到之前某一次的提交（时光倒流）
git reset --hard c888a614e072e2这样便回到了支付功能的状态

----------------


当你接到一个修复一个代号101的bug的任务时，很自然地，你想创建一个分支issue-101来修复它，但是，等等，当前正在dev上进行的工作还没有提交：

并不是你不想提交，而是工作只进行到一半，还没法提交，预计完成还需1天时间。但是，必须在两个小时内修复该bug，怎么办？
幸好，Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作：

git stash

------------

git merge --no-ff (表示禁用Fast forward)

（当前分支master，合并的分支是dev）git merge --no-ff -m "注释" dev

-------------

git rebase

这就是rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。

---------------

