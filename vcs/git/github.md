# GitHub

Git托管平台

## 注册

1. 访问<https://github.com>, 进行注册
2. 依次点击`settings/Profile`，修改个人信息
3. 依次点击`settings/Email`，修改邮件地址
3. 依次点击`settings/Notifications`，修改通知方式

## 派生项目

1. 找到想要派生的GitHub项目，点击`Fork`按钮，会在自己的Github上创建一个副本仓库
2. 克隆仓库到本地
3. 创建新的分支，在该分支上进行修改，并推送到仓库中
4. 点击`Pull Request`按钮，将合并请求发送给项目的拥有者

## 维护项目

创建、维护和管理自己的项目

### 创建版本库

点击`New respository`按钮，填写版本库信息

### 访问版本库

#### HTTP访问

使用`https://github.com/<username>/<repo>`地址访问版本库

#### SSH访问

1. 执行`ssh-keygen`命令，生成`id_rsa`私钥，`id_rsa.pub`公钥的密钥对
2. 访问<https://github.com>，依次点击`settings/SSH and GPG keys/New SSH Key`，Key中填写id_rsa.pub的内容
3. 使用`git@github.com:<username>/<repo>`地址访问版本库

### 添加合作者

进入GitHub上的某个仓库页，依次点击`settings/Collaborators`，添加合作者

## 管理组织

1. 点击`New organization`，创建组织
2. 管理团队成员及版本库权限