# Git

分布式版本控制系统

## 目录

## 参考资料

* [git-book](https://github.com/ninghao/git-book)
* [Pro Git](https://bingohuang.gitbooks.io/progit2/content/)
* [git权威指南](http://www.worldhello.net/gotgit/)


# 特点

## 直接记录快照，而非差异比较

差异流

![差异流](images/deltas.png)

快照流

![快照流](images/snapshots.png)

## 近乎所有操作都是本地执行

因为你在本地磁盘上就有项目的完整历史，所以绝大多数操作都只需要访问本地文件和资源，看起来瞬间完成

## Git 保证完整性

Git 中所有数据在存储前都计算校验和，然后以校验和来引用

## Git 一般只添加数据

你执行的 Git 操作，几乎只往 Git 数据库中增加数据


# 概念

## 工作区域

* Git 仓库目录： Git 用来保存项目的元数据和对象数据库的地方
* 工作目录：对项目的某个版本独立提取出来的内容
* 暂存区域：保存了下次将提交的文件列表信息

![工作区域](images/areas.png)

## 工作流程

1. 在工作目录中修改文件
2. 暂存文件，将文件的快照放入暂存区域
3. 提交更新，找到暂存区域的文件，将快照永久性存储到 Git 仓库目录

## 文件状态

* 已修改：作了修改但还没有放到暂存区域
* 已暂存：作了修改并已放入暂存区域
* 已提交：Git 目录中保存着的特定版本文件

## 模式

* 命令行：使用命令行操作Git
* GUI：使用GUI界面操作Git


# 安装

## 在windows上安装

有几种安装方法

* 安装[cmder](http://cmder.net/)的full版本
* 安装[msysgit](https://git-for-windows.github.io/)
* 安装[GitHub for Windows](https://desktop.github.com/)


# 配置

## 优先级

下一级别覆盖上一级别

* /etc/config: 系统配置，使用`git config --system`命令进行配置
* ~/.gitconfig或~/.config/git/config: 当前用户配置，使用`git config --global`命令进行配置
* .git/config: 当前仓库配置，使用`git config`命令进行配置