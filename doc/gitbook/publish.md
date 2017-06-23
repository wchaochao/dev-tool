# 发布

可发布到gitbook, github, github pages上

依赖：git

## 发布到gitbook上

1. 登录gitbook.com，创建书籍，获得该书籍的仓库地址：<https://git.gitbook.com/username/bookname.git>
2. 本地使用git将代码提交到gitbook仓库

## 发布到github上

1. 登录github.com，创建仓库，获得仓库地址：<https://github.com/username/repo.git>
2. 登录gitbook.com，创建书籍，并链接到github上的仓库
3. 本地使用git将代码提交到github仓库

## 发布到github pages上

1. 登录github.com，创建仓库，并创建ph-pages分支
2. 本地master分支目录生成静态网站，并复制到本地ph-pages分支上
3. 本地使用git将代码提交到ph-pages分支
4. 在<https://username.github.io/repo>查看静态网站