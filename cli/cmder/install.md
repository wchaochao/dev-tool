# 安装

从[cmder官网](http://cmder.net/)上下载压缩档，即压即用

* mini版：无内建msysgit工具
* full版: 有内建msysgit工具

## 设置

### 添加到环境变量

把Cmder.exe和git.exe/gitk.exe/git-gui.exe存放的目录添加到系统环境变量中

### 添加到右键菜单

以管理员身份打开cmder, 执行`Cmder.exe /REGISTER ALL`命令

### 默认设置

`windows+alt+p`打开设置页面，点击Startup，Specified named task选择Cmder as Admin

### 修改提示符

将vendor目录下的clink.lua第41行`local cmder_prompt = "\x1b[1;32;40m{cwd} {Git}{hg} \n\x1b[1;30;40m{lamd} \x1b[0m"` 里的{lamb}改为$
