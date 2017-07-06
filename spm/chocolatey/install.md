# 安装

1. 新建一个环境变量ChocolateyInstall，设定Chocolatey安装的位置
2. 以管理员身份运行cmd，执行以下命令

    ```
    @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
    ```

3. 将choco.exe存放的目录添加到系统环境变量中

## 自定义软件安装位置

1. 打开cmder, 执行`regedit`命令, 打开注册表
2. 依次展开`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`, 修改右侧窗口的`ProgramFilesDir`, `ProgramFilesDir(x86)`项, 如改为`D:\`
3. 重启电脑