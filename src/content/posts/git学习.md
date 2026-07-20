---
title: git学习
published: 2026-07-20
description: ''
image: ''
tags: []
category: Examples
draft: false 
lang: ''
---

# git学习笔记



## 1、git初始化

任一文件夹被git管理之后都会生成一个`.git`文件，表示该项目文件夹被git管理

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi0mpcZlat2794LlA-PRIM6BtAFFTYAAIcHQACFvnoVoV7IrnQ7tygPQQ.png)

在`.gitignore`中可声明不需要被git管理的文件或目录

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi02pcZq-hVxytllvB-U5JUnmROH3sAAIdHQACFvnoVv-yViUKNHMCPQQ.png)


### 2. commit提交

git仓库的每一次提交都会被记录，多次提交可形成一条可回溯的历史链路

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi1mpcjfzT98m0vvN6gc9mTzbgNt5tAAKGHQACFvnoVos0TGQAAeN_Sj0E.png)

在pycharm中，git日志里面可显示每一次提交的记录，回溯方式有：
- 对**最新**一次的历史记录**撤销提交**，只能撤回最后一次的commit
- 还原任意一次历史提交，可选中这一次记录，点击**还原提交**，git会生成一个与这次提交操作相反的提交来抵消掉这次提交，对应的`git revert`命令
- 若回溯之后代码没有变化，可以点击**蓝体**字文件，选择**回滚**来更新代码
  
![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi12pcjsM_RhzfbWV0ZjPcZt7_Wi3tAAKHHQACFvnoVpve1F-cbtKNPQQ.png)

### 3. branch分支

git可以在master/main主干上的任意一次历史提交上创建分支，分支只能继承主干上创建分支位置之前的提交记录，并且切换到分支上进行commit提交是不会出现在主干上，只有当分支与主干合并之后才会显示并修改，对应`git merge`命令
合并分支前需要先签出到主干，选择分支，“将该分支合并到master主干”

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi3Gpck7sV60FOvlE2aB2nY_hoM7xgAAKgHQACFvnoVvCQ3rWuka5kPQQ.png)

分支创建位置不设限制，指针HEAD，指向当前仓库、当前分支处于哪一次commit上。注意，**推送**时只会推送到暂存区里指针指向的位置以及之前的位置
- 点击**签出**相当于使用`git checkout`命令，只是把指针移动到了指定位置，实际暂存区并不会更新
- 点击**重置到当前分支**相当于使用`git reset`命令，指针和暂存区一并更新

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi3WpclRr08vua950KQCyM7xdmkT4tAAKlHQACFvnoVhktZ-8pFCwZPQQ.png)


### 4. git分区

![doocs](https://img2.nloln.de/file/BQACAgUAAyEGAASLVN5eAAJi32pcricYT_LROucwwbe76wMEQtSkAALfHQACFvnoVp2IY4kLtP8SPQQ.png)


- **工作区**：电脑磁盘的本地文件夹
- **暂存区**：使用`git add`让文件夹里的指定者加入git管辖的项目中
- **本地仓库**：git本地的项目存放仓库，使用`git commit`来提交
- **远程仓库**：将本地仓库的代码**推送**到服务器网站上开源，使用`git push`

本地和远端的开发管理方式有：

**1.** 在本地创建github共享（如使用pycharm等IDE工具先创建github项目），再使用add，commit，push，提交推送到远端仓库

**2**.选择github已存在的项目，使用`git clone`**克隆**到本地，再做修改以及推送

**3.** 若远端仓库有其他人贡献，代码发生改变，可以使用`git pull`拉取代码到本地来合并

###  参考网络视频


[【Git+Github核心概念大串讲，从零到一全攻略，详细实战教程】](https://www.bilibili.com/video/BV1ySLc6QEcB?vd_source=a0bed45866e68b9ace5f29bfeb70d8bb)

[【Pycharm中使用Git进行版本控制和协作编辑】](https://www.bilibili.com/video/BV1tfuKzzEE6?vd_source=a0bed45866e68b9ace5f29bfeb70d8bb)

[【651 pycharm操作git】](https://www.bilibili.com/video/BV18ykRYSEhU?vd_source=a0bed45866e68b9ace5f29bfeb70d8bb)