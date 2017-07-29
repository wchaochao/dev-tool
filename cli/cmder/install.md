# 安装

从[cmder官网](http://cmder.net/)上下载压缩档，即压即用

* `mini版`：无内建`msysgit`工具
* `full版`: 有内建`msysgit`工具

## 设置

### 添加到环境变量PATH

把`Cmder.exe`和`git.exe/gitk.exe/git-gui.exe`存放的目录添加到环境变量`Path`中

### 添加到右键菜单

以管理员身份打开`cmder`, 执行`Cmder.exe /REGISTER ALL`命令

### 默认设置

`windows+alt+p`打开设置页面，点击`Startup`, `Specified named task`选择`Cmder as Admin`

### 修改提示符

将`vendor`目录下的`clink.lua`第41行`local cmder_prompt = "\x1b[1;32;40m{cwd} {Git}{hg} \n\x1b[1;30;40m{lamd} \x1b[0m"` 里的`{lamb}`改为`$`
