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

本地磁盘上上有项目的完整历史，所以绝大多数操作都在本地进行


# 概念

## 工作区域

* Git仓库目录：Git用来保存项目的元数据和对象数据库的地方
* 工作目录：项目的某个快照
* 暂存区域：保存了下次将提交的文件快照

![工作区域](images/areas.png)

## 工作流程

1. 修改文件：在工作目录中修改文件
2. 暂存文件：将修改的文件添加到暂存区域
3. 提交更新：将暂存区域的快照永久性存储到Git仓库目录

## 文件状态

* 未跟踪：未纳入git管理
* 已跟踪：已纳入git管理
  * 未修改：未做修改
  * 已修改：作了修改但还未添加到暂存区域
  * 已暂存：作了修改并添加到暂存区域

![文件状态](images/lifecycle.png)

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

* /etc/config: 当前系统配置
* ~/.gitconfig或~/.config/git/config: 当前用户配置
* .git/config: 当前仓库配置

## 命令

```
usage: git config [<options>]

Config file location
    --global              use global config file
    --system              use system config file
    --local               use repository config file
    -f, --file <file>     use given config file
    --blob <blob-id>      read config from given blob object

Action
    --get                 get value: name [value-regex]
    --get-all             get all values: key [value-regex]
    --get-regexp          get values for regexp: name-regex [value-regex]
    --get-urlmatch        get value specific for the URL: section[.var] URL
    --replace-all         replace all matching variables: name value [value_regex]
    --add                 add a new variable: name value
    --unset               remove a variable: name [value-regex]
    --unset-all           remove all matches: name [value-regex]
    --rename-section      rename section: old-name new-name
    --remove-section      remove a section: name
    -l, --list            list all
    -e, --edit            open an editor
    --get-color           find the color configured: slot [default]
    --get-colorbool       find the color setting: slot [stdout-is-tty]

Type
    --bool                value is "true" or "false"
    --int                 value is decimal number
    --bool-or-int         value is --bool or --int
    --path                value is a path (file or directory name)

Other
    -z, --null            terminate values with NUL byte
    --name-only           show variable names only
    --includes            respect include directives on lookup
    --show-origin         show origin of config (file, standard input, blob, command line)
```

## 常用命令

* `git config --system`: 当前系统配置
* `git config --global`: 当前用户配置
* `git config`: 当前仓库配置
* `git config --global user.name "<username>"`: 配置全局用户名
* `git config --global user.email <useremail>`: 配置全局用户邮箱
* `git config -l`: 查看所有配置
* `git config -e`: 编辑配置文件


# 忽略文件

在.gitignore中列出要忽略的文件

## 规范

* 忽略空行和`#`开头的行
* 采用glob模式匹配
  * `*`: 匹配零个或任意个字符
  * `**`: 匹配任意中间目录
  * `?`: 匹配一个字符
  * `[]`: 匹配括号内的某一个字符
* `/`开头防止递归
* `/`结尾指定目录
* `!`表示不忽略


# 基础

Git完成各种工作中将要使用的各种基本命令

## 获取Git仓库

* `git init`: 当前目录初始化git仓库
* `git init [dir]`: 指定目录初始化git仓库
* `git clone <repo>`: 克隆git仓库
* `git clone <repo> <dir>`: 指定目录下克隆git仓库
* `git clone -b <branch> <repo>`: 克隆某个分支
* `git clone -o <remote> <repo>`: 设置远程连接名
* `git clone -c <key=value> <repo>`: 设置仓库配置

## 工作目录状态

* `git status`: 当前工作目录状态
* `git status -s`: 当前工作目录的简要状态
  * 右M 已修改但未暂存
  * 左M 修改并暂存
  * MM 暂存但又修改了
  * 左A 跟踪新文件
  * 右D 删除文件但未暂存
  * 左D 删除文件并暂存
  * 左R 重命名文件
  * ?? 未跟踪文件

## 比较

* `git diff`: 比较工作目录和暂存区
* `git diff <path...>`: 比较工作目录和暂存区的某些文件
* `git diff --cached`: 比较暂存区和本地仓库
* `git diff --cached <path...>`: 比较暂存区和本地仓库的某些文件
* `git diff --staged`: 比较暂存区和本地仓库

## 暂存

* `git add <file1, file2...>`: 跟踪新文件或暂存已修改的文件
* `git add <dir2, dir2...>`: 跟踪指定目录下的新文件或暂存指定目录下已修改的文件
* `git add -a`: 跟踪所有新文件或暂存所有已修改的文件

