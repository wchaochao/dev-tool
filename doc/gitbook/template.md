# 模板

Gitbook使用Numjunks和的模板语法

## 原样输出

```
{% raw %}
  这{{不会被处理}}
{% endraw %}
```

**注：**代码块中有模板时，本地编译会报错，需要用`{% raw %}{% endraw %}`包裹

## 全局变量

> * gitbook: gitbook信息
> * page: 当前页信息
> * file: 当前文件信息
> * readme: README信息
> * summary: SUMMARY信息
> * languages: LANGS信息
> * glossary: GLOSSARY信息
> * book: book.json中的配置信息

### Gitbook变量

> * gitbook.time: gitbook的运行时间
> * gitbbok.version: gitbook的版本号

### page变量

> * page.title: 页面标题
> * page.previous: 上一页
> * page.next: 下一页
> * page.dir: 文本方向

### file变量

> * file.path: 文件路径
> * file.type: 文件类型
> * file.mtime: 文件的最后修改时间

### output变量

> * output.name: 输出名称
> * output.format: 输出格式

### readme变量

> * readme.path: README的文件路径

### summary变量

> * summary.parts: 章节目录

### languages变量

> * languages.list: 语言列表

### glossary变量

> * golssary.path: GLOSSARY的文件路径

### book变量

> * book.language: book.json中的语言设置
> * book.[value]: book.json中的变量设置

```json
{
  "variables":{
    "hello":"hello everyone"
  }
}
```

## 输出变量

```
{% raw %}
  The author is {{book.author}}
{% endraw %}
```

## 过滤器

```
{% raw %}
  {{foo|capitalize}}
{% endraw %}
```

## set语句

设置变量

```
{% raw %}
  {% set version="1.0.0" %}

  Current Version is {{version}}
{% endraw %}
```

## if语句

条件判断

```
{% raw %}
  {% if hungry %}
    I am hungry
  {% elif tried %}
    I am tried
  {% else %}
    I am good
  {% endif %}
{% endraw %}
```

## for语句

循环

```
{% raw %}
  {% for article in book.articles %}
  * [{{article.title}}]({{article.path}})
  {% endfor %}
{% endraw %}
```

## 引用

引用本地文件

```
{% raw %}
  {% include "./test.md" %}
{% endraw %}
```

引用其他文件

```
{% raw %}
  {% include "git+https://user@hostname/project/blah.git/file#commit-ish"%}
{% endraw %}
```

## 继承

```
{% raw %}
  {% extends "./mypage.md" %}

  {% block pageContent %}
  # This is my page content
  {% endblock %}
{% endraw %}
```
