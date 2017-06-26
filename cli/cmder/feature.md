# 常用功能

## 快捷键

cmder

* <code>Ctrl+`</code>：显示/隐藏cmder
* `windows+alt+p`：打开设置页面

Tab

* `Ctrl+T`：新建标签
* `Ctrl+W`：关闭标签
* `Shift+Alt+n`：新建标签, 1-cmd, 2-PowerShell, 3-bash
* `Ctrl+Tab`：下一个标签
* `Ctrl+Shift+Tab`：上一个标签
* `Ctrl+n`：第n个标签
* `Alt+Enter`：全屏

shell

* `Ctrl+Alt+u`：上一级目录
* `End, Home, Ctrl`：行尾，行首，移动
* `Ctrl+R`：历史记录搜索
* `Shift+Mouse`：复制

## 模式

Task | Shell | Config
---------|----------|---------
 Cmder | cmd.exe | %CMDER_ROOT%\config\user-profile.cmd
 Cmder as Admin | cmd.exe | %CMDER_ROOT%\config\user-profile.cmd
 PowerShell | powershell.exe | $ENV:CMDER_ROOT\config\user-profile.ps1
 PowerShell as Admin | powershell.exe | $ENV:CMDER_ROOT\config\user-profile.ps1
 Bash | bash.exe | $CMDER_ROOT/config/user-profile.sh
 Bash as Admin | bash.exe | $CMDER_ROOT/config/user-profile.sh
 Mintty | bash.exe | $CMDER_ROOT/config/user-profile.sh
 Mintty as Admin | bash.exe | $CMDER_ROOT/config/user-profile.sh

## 别名

使用`alias`命令