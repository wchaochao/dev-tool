# 发布

可发布到`gitbook`, `github`, `github pages`上

依赖：`git`

## 发布到gitbook上

1. 登录<https://gitbook.com>，创建书籍，获得该书籍的仓库地址：<https://git.gitbook.com/username/bookname.git>
2. 本地使用`git`将代码提交到`gitbook`仓库

## 发布到github上

1. 登录<https://github.com>，创建仓库，获得仓库地址：<https://github.com/username/repo.git>
2. 登录<https://gitbook.com>，创建书籍，并链接到`github`上的仓库
3. 本地使用`git`将代码提交到`github`仓库

## 发布到github pages上

1. 登录<https://github.com>，创建仓库，并创建`ph-pages`分支
2. 本地`master`分支目录生成静态网站，并复制到本地`ph-pages`分支上
3. 本地使用`git`将代码提交到`ph-pages`分支
4. 在<https://username.github.io/repo>查看静态网站