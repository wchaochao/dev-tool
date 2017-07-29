# 签署

通过`GPG`来签署和验证工作

## GPG命令

* `gpg --gen-key`: 生成`gpg`密钥对
* `gpg --list-keys`: 查看`gpg`密钥对

## 配置

1. 本地执行`git config --global user.signingkey <pub>`命令，配置签署密钥
2. 将gpg公钥放入git服务器的GPG钥匙链中

## 常用命令

* `git tag -s`: 签署标签
* `git tag -v`: 验证签署标签
* `git commit -S`: 签署提交
* `git log --show-signature`: 签署提交历史
* `git pull --verify-signature`: `pull`时验证是否是有效签署提交
* `git merge --verify-signature`: `merge`时验证是否是有效签署提交
* `git merge -S`: 签署合并提交