# 配置

## 优先级

下一级别覆盖上一级别

* `git目录/etc/config`: 当前系统配置
* `~/.gitconfig或~/.config/git/config`: 当前用户配置
* `当前仓库目录/.git/config`: 当前仓库配置

## 配置命令

* `git config --system`: 当前系统配置
* `git config --global`: 当前用户配置
* `git config`: 当前仓库配置
* `git config -l`: 查看所有配置
* `git config -e`: 编辑配置文件

## 常用配置

### 用户名和邮箱

* `git config --global user.name "<username>"`: 设置用户名
* `git config --global user.email <useremail>`: 设置邮箱

### 文本编辑器

* `git config --global core.editor <editor>`: 设置文本编辑器(`editor`为启动编辑器的命令)，默认为`vi`

### 分页器

* `git config --global core.pager <'' | less | more>`: 设置分页器，默认为`less`

### 忽略文件

* `git config --global core.excludesfile <file>`: 设置全局忽略文件

### 格式化

* `git config --global core.autocrlf <true | false | input>`: 设置换行符

### 提交信息模板

* `git config --global commit.template <file>`: 设置提交信息模板

### 着色

* `git config --global color.ui [auto | false | always]`: 是否着色，默认为`auto`
* `git conifg --global color.[branch|diff|interactive|status] '<foreground background font>'`: 着什么色

### 合并和比较工具

1. 使用`chocolatey`安装`P4Merge`
2. 配置合并和比较工具
3. 使用`git difftool`命令进行比较，使用`git mergetool`解决合并冲突

```
git config --global diff.tool p4merge
git config --global difftool.p4merge.path <p4merge.exe路径>

git config --global merge.tool p4merge
git config --global mergetool.p4merge.path <p4merge.exe路径>
```

### GPG签署密钥

* `git config --global user.signingkey <gpg-key-id>`: 设置GPG签署密钥

### 凭证

使用HTTP协议连接时，需要提供凭证，默认每次连接都询问用户名和密码

* `git config --global credential.helper cache --timeout <n>`: 将凭证存放到内存中一段时间
* `git config --global credential.helper --file <path>`: 将凭证明文存放到文件中

### SSH

使用SSH连接时，需要将本机的SSH公钥提供给git服务器，每次连接都不需凭证

1. 执行`ssh-keygen`命令，生成SSH密钥对
2. 将SSH公钥提供给git服务器

### 别名

* `git config --global alias.st status`
* `git config --global alias.ci commit`
* `git config --global alias.br branch`
* `git config --global alias.co checkout`
* `git config --global alias.unstage 'reset HEAD'`
* `git config --global alias.undo 'checkout --'`
* `git config --global alias.last 'log -1'`
* `git conifg --global alias.lg 'log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Cre'`

### 中文乱码

* `git config --global gui.encoding utf-8`: gui中文乱码