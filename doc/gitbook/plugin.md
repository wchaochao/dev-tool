# 插件

gitbook的扩展功能

## 查找插件

<https://plugins.gitbook.com/>

## 安装插件

1. 在book.json中添加插件和插件配置
2. 使用gitbook install命令安装插件

## 默认插件

> * [highlight](https://plugins.gitbook.com/plugin/highlight): 代码高亮
> * [search](https://plugins.gitbook.com/plugin/search): 搜索
> * [sharing](https://plugins.gitbook.com/plugin/sharing): 分享
> * [fontsettings](https://plugins.gitbook.com/plugin/fontsettings): 字体设置
> * [livereload](https://plugins.gitbook.com/plugin/livereload): 自动刷新

## 常用插件

实用插件

### [Disqus](https://plugins.gitbook.com/plugin/disqus)

添加disqus评论

```json
{
  "plugins": [
    "disqus"
  ],
  "pluginsConfig": {
    "disqus": {
      "shortName": "gitbookuse"
    }
  }
}
```

### [Search Pro](https://plugins.gitbook.com/plugin/search-pro)

支持中文搜索

```json
{
  "plugins": [
    "-lunr",
    "-search",
    "search-pro"
  ]
}
```

### [Prism](https://plugins.gitbook.com/plugin/prism)

代码高亮

```json
{
  "plugins": ["prism", "-highlight"],
  "pluginsConfig": {
    "prism": {
      "css": [
        "prismjs/themes/prism-solarizedlight.css"
      ]
    }
  }
}
```

### [Github](https://plugins.gitbook.com/plugin/github)

添加Github图标

```json
{
  "plugins": [
    "github"
  ],
  "pluginsConfig": {
    "github": {
      "url": "https://github.com/username/repo"
    }
  }
}
```

### [Github Buttons](https://plugins.gitbook.com/plugin/github-buttons)

添加github的star, watch, fork按钮

```json
{
  "plugins": [
    "github-buttons"
  ],
  "pluginsConfig": {
    "github-buttons": {
      "repo": "username/repo",
      "types": [
        "star",
        "watch",
        "fork"
      ],
      "size": "small"
    }
  }
}
```

### [Splitter](https://plugins.gitbook.com/plugin/splitter)

调节侧边栏宽度

```json
{
  "plugins": [
    "splitter"
  ]
}
```

### [Sharing](https://plugins.gitbook.com/plugin/sharing)

分享，gitbook的默认插件

```json
{
  "pluginsConfig": {
    "sharing": {
      "weibo": true,
      "facebook": true,
      "twitter": true,
      "google": false,
      "instapaper": false,
      "vk": false,
      "all": [
        "facebook", "google", "twitter",
        "weibo", "instapaper"
      ]
    }
  }
}
```

### [Tbfed-pagefooter](https://plugins.gitbook.com/plugin/tbfed-pagefooter)

添加页脚

```json
{
  "plugins": [
    "tbfed-pagefooter"
  ],
  "pluginsConfig": {
    "tbfed-pagefooter": {
      "copyright": "Copyright &copy zhangjikai.com 2015",
      "modify_label": "该文件修订时间：",
      "modify_format": "YYYY-MM-DD HH:mm:ss"
    }
  }
}
```

### [Toggle Chapters](https://plugins.gitbook.com/plugin/toggle-chapters)

折叠章节目录

```json
{
  "plugins": ["toggle-chapters"]
}
```

### [Include Codeblock](https://plugins.gitbook.com/plugin/include-codeblock)

使用代码块格式显示文件内容

```json
{
  "plugins": [
    "include-codeblock"
  ]
}
```

### [Donate]((https://plugins.gitbook.com/plugin/donate))

打赏

```json
{
  "plugins": [
    "donate"
  ],
  "pluginsConfig": {
    "donate": {
      "wechat": "/resource/weixin.png",
      "alipay": "/resource/alipay.png",
      "title": "",
      "button": "赏",
      "alipayText": "支付宝打赏",
      "wechatText": "微信打赏"
    }
  }
}
```

### [Simple-page-toc](https://plugins.gitbook.com/plugin/simple-page-toc)

自动生成本页目录

```json
{
  "plugins": [
    "simple-page-toc"
  ],
  "pluginsConfig": {
    "simple-page-toc": {
      "maxDepth": 3,
      "skipFirstH1": true
    }
  }
}
```

### [Anchors](https://plugins.gitbook.com/plugin/anchors)

添加Github风格的锚点样式

```json
{
  "plugins": ["anchors"]
}
```

### [Anchor-navigation-ex](https://plugins.gitbook.com/plugin/anchor-navigation-ex)

锚点导航

```json
{
  "plugins": [
    "anchor-navigation-ex"
  ],
  "pluginsConfig": {
    "anchor-navigation-ex": {
      "isRewritePageTitle": true,
      "isShowTocTitleIcon": true,
      "tocLevel1Icon": "fa fa-hand-o-right",
      "tocLevel2Icon": "fa fa-hand-o-right",
      "tocLevel3Icon": "fa fa-hand-o-right"
    }
  }
}
```

### [Todo](https://plugins.gitbook.com/plugin/todo)

添加Todo功能

```json
{
  "plugins": ["todo"]
}
```