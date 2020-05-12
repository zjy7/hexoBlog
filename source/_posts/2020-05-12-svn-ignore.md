---
title: svn ignore
date: 2020-05-12 13:29:34
tags:
categories:
- Code
---
svn ignore 的用法（忽略文件及目录）
若想创建了一个文件夹，并且把它加入版本控制，但忽略文件夹中的所有文件的内容：

$ svn mkdir spool
$ svn propset svn:ignore '*' spool
$ svn ci -m 'Adding "spool" and ignoring its contents.'

若想创建一个文件夹，但不加入版本控制，即忽略这个文件夹：

$ mkdir spool
$ svn propset svn:ignore 'spool' .
$ svn ci -m 'Ignoring a directory called "spool".'

若已经创建了文件夹，并加入了版本控制，现在想忽略这个文件夹，但要保持文件夹的内容：

$ svn export spool spool-tmp
$ svn rm spool
$ svn ci -m 'Removing inadvertently added directory "spool".'
$ mv spool-tmp spool
$ svn propset svn:ignore 'spool' .

$ svn ci -m 'Ignoring a directory called "spool".'