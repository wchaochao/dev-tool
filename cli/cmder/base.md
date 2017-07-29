# 命令行基础

## 帮助

* 帮助信息：`<command> --help`
* 使用手册：`man <command>`
* 解释：<https://explainshell.com/>

## 工作目录

当前所在的位置

* 输出工作目录：`pwd`
* 改变工作目录：`cd [path]`, `cd /d [drive:][path]`

## 路径

* 层级：Linux/Unix层级关系使用`/`表示，Windows使用`\`表示
* 绝对路径：Linux/Unix以`/`开头，Windows以`盘符:\`开头
* 相对路径：不以绝对开头，相对当前目录而言
* 特殊符号：`~`-用户主目录，`.`-当前目录，`..`-父目录
* 通配符：可使用通配符来匹配文件或目录