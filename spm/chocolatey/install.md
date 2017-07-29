# 安装

1. 新建一个环境变量`ChocolateyInstall`，设定`Chocolatey`安装的位置
2. 以管理员身份运行`cmd`，执行以下命令

    ```
    @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
    ```

3. 将`choco.exe`存放的目录添加到环境变量`Path`中

## 自定义软件安装位置

1. 打开`cmder`, 执行`regedit`命令, 打开注册表
2. 依次展开`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`, 修改右侧窗口的`ProgramFilesDir`, `ProgramFilesDir(x86)`项, 如改为`D:\`
3. 重启电脑