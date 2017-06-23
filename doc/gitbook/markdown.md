# Markdown

Gitbook默认使用[Markdown](../markdown/README.md)语法并有所扩展

## 扩展

### 字体

```markdown
~~删除线~~
```

### 脚注

```markdown
脚注参考前的文本。[^2]

[^2]:评论要包括在脚注中。
```

### 代码块和语法高亮

    ```javascript
    var s="javascript语法高亮"
    ```

    ```
    无指定语言，无语法高亮
    ```

### 表格

```markdown
| Tables        | Are           | Cool  |
|:-------------:|:-------------:|:-----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

### Youtube视频

```html
<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg"
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
```