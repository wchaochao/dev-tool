# 安装

1. 新建一个环境变量ChocolateyInstall，设定Chocolatey安装的位置
2. 以管理员身份运行cmd，执行以下命令

    ```
    @powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
    ```

3. 将choco.exe存放的目录添加到系统环境变量中