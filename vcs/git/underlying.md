# 底层命令

底层命令反应Git内部的工作机制

## .git目录结构

```
HEAD: 当前分支
index: 暂存区
objects: 存储数据
refs: 引用
config: 当前仓库配置
hooks: Git钩子
```

## Git对象

### 存储

1. 生成头部信息，`header='<类型> <长度>\u0000'`
2. 拼接头部信息和原始数据，`store=header+content`
3. 计算SHA-1值，`sha1 = Digest::SHA1.hexdigest(store)`
4. 压缩内容，`zlib_content = Zlib::Deflate.deflate(store)`
5. 写入磁盘，`path = '.git/objects/' + sha1[0,2] + '/' + sha1[2,38]`

### 命令

* `git hash-object -w <file>`: 将文件转换为blob对象存储，返回对应hash键值
* `git update-index [--add] <file>`: 更新暂存区
* `git write-tree`: 暂存区生成tree对象
* `echo '<message>' | git commit-tree <tree-hash> -p <parent-hash>`: 生成commit对象
* `git cat-file -p <hash>`: 查看hash键值对应的文件对象、树对象、提交对象

## Git引用

* `git update-ref refs/heads/master <commit-hash>`: 设置master分支指向某个提交对象
* `git symbolic-ref HEAD refs/heads/master`: 设置HEAD指向master分支
* `git update-ref refs/tags/v1.0 <commit-hash>`: 设置轻量标签永久指向某个提交对象
* `cat .git/refs/remotes/origin/master`: 查看只读的远程引用

## 包文件

* `git gc`: 打包对象
* `git verify-pack -v .git/objects/pack/pack-978e03944f5c581011e6998cd0e9e30000905586.idx`: 查看已打包的内容

## 引用规格

```
[remote "origin"]
  url = https://github.com/schacon/simplegit-progit // 远程仓库地址
  fetch = +refs/heads/*:refs/remotes/origin/* //fetch时默认将远程版本库中refs/heads/*的引用导入到本地的refs/remotes/origin位置
  push = refs/heads/master:refs/heads/qa/master //push时默认将本地refs/heads/master章的引用导入到远程版本库的refs/heads/qa/master位置
```

## 数据维护

* `git gc`: 打包对象
* `git reflog`: 查看HEAD引用日志
* `git log -g`: 查看HEAD引用日志详情
* `git fsck --full`: 查看未被引用的数据对象
* `git filter-branch`: 批量修改提交历史