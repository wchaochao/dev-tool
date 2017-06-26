# 常用命令

## 列出

ls [option] [path]

* `ls`：列出当前目录内容
* `ls [path]`：列出指定位置的内容
* `ls -a [path]`：列出所有内容
* `ls -l [path]`：以长格式列出
* `ls -lt [path]`：按最后修改时间排序

## 创建

* `mkdir [path]`：创建目录
* `touch [file]`：创建文件
* `echo '[message]' >> [file]`： 追加信息
* `cat [file]`：输出文件内容

## 复制

cp [target] [destination]

* `cp [file1] [file2]`：复制文件
* `cp -r [dir1] [dir2]`：复制目录

## 重命名/移动

move [target] [destination]：重命名或移动

## 删除

rm [path]

* `rm [file]`：删除文件
* `rm -rf [dir]`：删除目录

## 编辑文件

vi [file]：编辑文件

* `i`：进入编辑模式
* `esc`：退出编辑模式
* `/`：搜索
* `:wq`：保存并退出
* `:q!`：不保存退出

## 查看文件

* `cat [file]`：输出文件
* `tail [file]`：输出文件的最后一小部分