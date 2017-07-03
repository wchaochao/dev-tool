# Git

分布式版本控制系统

## 目录

## 参考资料

* [git-book](https://github.com/ninghao/git-book)
* [Pro Git](https://bingohuang.gitbooks.io/progit2/content/)


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

* /etc/config: 当前系统配置(git目录下)
* ~/.gitconfig或~/.config/git/config: 当前用户配置
* .git/config: 当前仓库配置

## 常用配置

### 全局用户名和邮箱

* `git config --global user.name "<username>"`: 配置全局用户名
* `git config --global user.email <useremail>`: 配置全局用户邮箱

### 全局编辑器

* `git config --global core.editor <editor>`: 配置全局编辑器(editor为启动编辑器的命令)

### 别名

* git config --global alias.st status
* git config --global alias.ci commit
* git config --global alias.br branch
* git config --global alias.co checkout
* git config --global alias.unstage 'reset HEAD'
* git config --global alias.undo 'checkout --'
* git config --global alias.last 'log -1'
* git conifg --global alias.lg 'log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Cre'


## 配置命令

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

## 帮助

* `git help <command>`: 帮助文档

## 获取Git仓库

* `git init`: 当前目录初始化git仓库
* `git init [dir]`: 指定目录初始化git仓库
* `git clone <repo>`: 当前目录克隆git仓库
* `git clone <repo> <dir>`: 指定目录克隆git仓库
* `git clone -b <branch> <repo>`: 克隆指定分支
* `git clone -o <remote-name> <repo>`: 指定远程仓库的简写
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
* `git diff HEAD`: 比较工作目录和本地仓库

## 暂存

* `git add <path...>`: 跟踪新文件或暂存已修改的文件
* `git add .`: 跟踪本目录下的新文件或暂存本目录下的已修改文件
* `git add -A`: 跟踪所有新文件或暂存所有已修改的文件
* `git rm <path...>`: 删除文件并暂存
* `git rm --cached <path...>`: 删除暂存区的文件
* `git mv <target> <destination>`: 重命名文件并暂存

## 撤销

* `git reset HEAD <file>`: 撤销暂存
* `git checkout -- <file>`: 撤销修改

## 提交

* `git commit`: 启动配置的编辑器输入提交信息并提交
* `git commit -m '<message>'`: 指定提交信息并提交
* `git commit -a`: 暂存所有已跟踪的文件并提交
* `git commit --amend`: 重新提交

## 提交历史

* `git log`: 显示提交历史
* `git log -p`: 显示每次提交的详细更改信息
* `git log --stat`: 显示每次提交的简要更改信息
* `git log --graph`: 图表显示
* `git log --pretty=<format>`: 指定显示的格式
  * oneline 一行显示commit, message
  * short 分行显示commit, Author, message
  * full 分行显示commit, Author, Commit, message
  * fuller 分行显示commit, Author, AuthorDate, Commit, CommitDate, message
  * format:"<options>" 自定义格式
    * %H|%h commit的完整|简短哈希字符串
    * %T|%t tree的完整|简短哈希字符串
    * %P|%p parent的完整|简短哈希字符串
    * %an|%ae|%ad|%ar 作者名字|邮箱|提交日期(--date= 时间格式)|提交日期(按多久以前的方式显示)
    * %cn|%ce|%cd|%cr 提交者名字|邮箱|提交日期(--date= 时间格式)|提交日期(按多久以前的方式显示)
    * %s message
* git log <filter> 筛选提交历史
  * -<n> 仅显示最近的 n 条提交
  * --since|--after 仅显示指定时间之后的提交
  * --until|--before 仅显示指定时间之前的提交
  * --author 仅显示指定作者相关的提交
  * --committer 仅显示指定提交者相关的提交
  * --grep 仅显示含指定关键字的提交
  * --no-merges 仅显示未合并的提交
  --all-match 满足所有条件的提交

## 标签

* `git tag`: 显示所有标签
* `git show <tag>`: 显示某个标签的信息
* `git tab <tag>`: 创建轻量标签
* `git tab -a <tag> -m "<message>"`: 创建附注标签
* `git tab -a <tag> <commit>`: 给指定提交创建附注标签
* `git push <remote-name> <tag>`: 推送某个标签
* `git push <remote-name> --tags`: 推送所有标签
* ··

## 远程仓库

* `git remote`: 远程仓库的简写
* `git remote -v`: 远程仓库的简写和url
* `git remote show [remote-name]`: 显示远程仓库的详细信息
* `git remote add <remote-name> <url>`: 添加远程仓库
* `git remote rm <remote-name>`: 移除远程仓库
* `git remote rename <remote-name1> <remote-name2>`: 重命名远程仓库
* `git fetch [remote-name]`: 抓取远程仓库的所有分支的数据
* `git pull [remote-name] [branch]`: 获取跟踪的远程分支的数据并合并到本地仓库的对应分支
* `git push [remote-name] [branch]`: 推送本地分支的数据到对应的远程分支


# 分支

提交对象

![提交对象](images/commit-and-tree.png)

提交链

![提交链](images/commits-and-parents.png)

分支

![分支](images/branch-and-history.png)

创建分支

git branch <branch>