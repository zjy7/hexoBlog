---
title: 解决github上传ssh-key后仍须输入密码的问题
tags:
categories:
- Code
---

这种事情通常发生在更换机器后克隆自己仓库的时候，通常我们会使用https方式克隆


git clone https://github.com/Name/project.git


这样便会在你git push时候要求输入用户名和密码


***解决的方法是使用ssh方式克隆仓库***

git clone git@github.com:Name/project.git


当如，如果你已经用https方式克隆了仓库，就不必删除仓库重新克隆，只需将 .git/config文件中的

url = https://github.com/Name/project.git

一行改为

url = git@github.com:Name/project.git

即可。