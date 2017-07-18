# 文件

## 忽略文件

在`.gitignore`中列出要忽略的文件

### 规范

* 忽略空行和`#`开头的行
* 采用glob模式匹配
  * `*`: 匹配零个或任意个字符
  * `**`: 匹配任意中间目录
  * `?`: 匹配一个字符
  * `[]`: 匹配括号内的某一个字符
* `/`开头防止递归
* `/`结尾指定目录
* `!`表示不忽略

## 属性文件

在`.gitattributes`中针对特定的路径配置某些设置项

### 识别二进制文件

```
*.pbxproj binary
```

### 比较二进制文件

```
*.docx diff=word

git config diff.word.textconv docx2txt
```

### 导出忽略

```
test/ export-ignore
```

### 合并策略

```
database.xml merge=ours
```