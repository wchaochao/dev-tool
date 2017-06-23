# 目录结构

> * README.md: 介绍
> * SUMMARY.md: 章节目录
> * LANGS.md: 多语言
> * GLOSSARY.md: 术语清单
> * cover.jpg: 大封面
> * cover_small.jpg: 小封面
> * .gitignore: git的忽略文件
> * .bookignore: book的忽略文件
> * .ignore: 忽略文件
> * book.json: 配置文件

## README.md

* 书本介绍
* 若不在SUMMARY中，会自动添加为SUMMARY的第一个章节
* 可在book.json中设置README.md的替换文件

```json
{
  "structure":{
    "readme":"myIntro.md"
  }
}
```

## SUMMARY.md

定义书本的章节结构

```markdown
# Summary

* [介绍](README.md)

### 第一部分

* [卷一](part1/README.md)
  * [章节1](part1/chapter1.md)
  * [章节2](part1/chapter2.md)
* [卷二](part2/README.md)
  * [章节1](part2/chapter1.md)
  * [章节2](part2/chapter2.md)
```

## LANGS.md

使用多语言

```markdown
# Languages

* [英语](en/)
* [法语](fr/)
* [中文](zh/)
```

## GLOSSORY.md

术语表

```markdown
# Glossary

## 术语
这个术语的描述
```

## 封面

可以使用autocover插件来生成封面

```markdown
|                     |     大      |       小          |
|:-------------------:|:-----------:|:-----------------:|
|       **文件**      | `cover.jpg` | `cover_small.jpg` |
|    **大小(像素)**   |  1800x2360  |      200x262      |
```

## 忽略文件

文件格式

```markdown
# 忽略test.md文件
test.md

# 忽略bin文件夹
bin/*
```

## book.json文件

配置文件

```json
{
  "root": "./", // 根文件夹路径
  "title": "myBook", // 标题，默认从README.md提取
  "description": "This is such a great book!", // 描述，默认从README.md的第一段中提取
  "author": "jack", // 作者，默认从gitbook.com上提取
  "isbn": "978-3-16-148410-0", // 国际码ISBN
  "language": "en", // 语言，默认为en
  "direction": "rtl", // 文字方向，默认由语言决定
  "gitbook": ">=2.0.0", // gitbook版本
  "structure":{ // 设置文件路径
    "readme": "README.md",
    "summary": "SUMMARY.md",
    "language": "LANGS.md",
    "glossary": "GLOSSARY.md"
  },
  "variables":{ // 设置变量
    "hello": "hello world"
  },
  "links" : { // 左侧导航栏添加链接
    "sidebar" : {
      "github" : "https://github.com"
    }
  },
  "styles": { // 各种输出格式的样式
    "website": "styles/website.css",
    "ebook": "styles/ebook.css",
    "pdf": "styles/pdf.css",
    "mobi": "styles/mobi.css",
    "epub": "styles/epub.css"
  },
  "pdf": { // pdf输出设置
    "pageNumbers": true,
    "fontSize": 12,
    "fontFamily": "Arial",
    "pagerSize": "a4",
    "margin":{
      "top": 56,
      "bottom": 56,
      "right": 62,
      "left": 62
    }
  },
  "plugins": ["mathjax"], // gitbook插件
  "pluginsConfig": { // 插件配置
    "myPlugin":{
      "message":"Hello world"
    }
  }
}
```