---
title: git入门--常用命令
date: 2019-01-16 23:20:54
tags:
---
# git入门--常用命令
1. git init
  - git init 的作用是初始化本地仓库 .git 
  ![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/002.png?raw=true "git init")
  - 执行git init 前后分别执行ls -a命令查看文件，可以发现多了一个.git目录，这就是我们初始化的一个本地仓库 
2. git add  将文件添加到 **暂存区**
  - 当本地仓库文件发生变动时，如果想让改动保存到仓库里，需要先 git add 文件名 或者 git add .（保存当前目录下的所有变动）
  ![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/003.png?raw=true "git add")

3. git commit -m "改动信息"  
  - 正式提交变动，将暂存区的变动提交至 .git 仓库
  ![blockchain](https://github.com/AutumnQqt/blog-generator/blob/master/imgs/003.png?raw=true "git commit")