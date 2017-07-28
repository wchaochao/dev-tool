# 常用命令

## 列出

* `ls`：列出当前目录内容
* `ls <path>`：列出指定位置的内容
* `ls -a [path]`：列出所有内容
* `ls -l [path]`：以长格式列出
* `ls -t [path]`：按最后修改时间排序
* `ls -alt [path]`：以长格式列出所有内容并按最后修改时间排序

## 目录结构

* `tree <dir>`: 查看指定目录的目录结构

## 创建

* `md <path>`：创建目录
* `touch <file>`：创建文件

## 复制

* `cp <file1...> <dir>`: 复制多个文件
* `cp <file1> <file2>`：复制文件并重命名
* `cp -r <dir1> <dir2>`：复制目录

## 移动

* `mv <file1...> <div>`: 移动多个文件
* `mv <file1> <file2>`: 移动文件并重命名
* `move <dir1> <dir2>`：移动目录

## 删除

* `rm <file>`：删除文件
* `rm -r <dir>`：删除目录

## 编辑文件

`vi <file>`：编辑文件

* `i`：进入编辑模式
* `esc`：退出编辑模式
* `/`：搜索
* `:wq`：保存并退出
* `:q!`：不保存退出

## 查看文件

* `cat <file>`：输出文件内容
* `tail <file>`：输出文件的最后一小部分

## 文件操作

* `wc <file>`: 输出文件的行数、字符数、字节数
* `sort <file>`: 按字母给行排序
* `uniq <file>`: 忽略相同并相邻的行

## 查找

* `grep <regexp> <file>`: 在文件中查找
* `grep -i <regexp> <file>`: 忽略大小写
* `grep -R <regexp> <dir>`: 在目录中查找

## 替换

* `sed 's/<search>/<replace>' <file>`: 替换首个
* `sed 's/<search>/<replace>/g' <file>`: 替换全部

## 输出

* `echo '[message]'`: 输出信息

## 导向

* `>`: 将输出导入到文件中并覆盖原来的内容
* `>>`: 将输出添加到文件末尾
* `<`: 将输入导入到命令
* `|`: 将左边的输出导入到右边的命令

```
echo '[message]' > <file>： 输出信息到文件，覆盖文件原来的内容
echo '[message]' >> <file>： 输出信息到文件，添加到文件末尾
cat <file1> > <file>： 输出文件内容到指定文件，覆盖文件原来的内容
cat <file1> >> <file>： 输出文件内容到指定文件，添加到文件末尾
cat < <file>: 输出文件内容
cat <file1> | sort > <file>: 将文件内容排序后导入到指定文件
```

## 辅助

* `clear`: 清屏
* `history`: 命令历史
* `<editor> <file>`: 用编辑器打开文件