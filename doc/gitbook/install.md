# 安装

依赖：nodejs, npm

## 安装gitbook-cli{#install}

```
安装
npm i -g gitbook-cli

是否安装成功
gitbook -V
```

## gitbook-cli命令

gitbook help查看gitbook命令

```
    build [book] [output]       build a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)
        --[no-]timing           Print timing debug information (Default is false)

    serve [book] [output]       serve the book as a website for testing
        --port                  Port for server to listen on (Default is 4000)
        --lrport                Port for livereload server to listen on (Default is 35729)
        --[no-]watch            Enable file watcher and live reloading (Default is true)
        --[no-]live             Enable live reloading (Default is true)
        --[no-]open             Enable opening book in browser (Default is false)
        --browser               Specify browser for opening book (Default is )
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
        --format                Format to build to (Default is website; Values are website, json, ebook)

    install [book]              install all plugins dependencies
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    parse [book]                parse and print debug information about a book
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    init [book]                 setup and create files for chapters
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    pdf [book] [output]         build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    epub [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

    mobi [book] [output]        build a book into an ebook file
        --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

```

gitbook -h查看gitbook-cli命令

```

  Usage: gitbook [options] [command]


  Commands:

    ls                        List versions installed locally
    current                   Display currently activated version
    ls-remote                 List remote versions available for install
    fetch [version]           Download and install a <version>
    alias [folder] [version]  Set an alias named <version> pointing to <folder>
    uninstall [version]       Uninstall a version
    update [tag]              Update to the latest version of GitBook
    help                      List commands for GitBook
    *                         run a command with a specific gitbook version

  Options:

    -h, --help               output usage information
    -v, --gitbook [version]  specify GitBook version to use
    -d, --debug              enable verbose error
    -V, --version            Display running versions of gitbook and gitbook-cli

```

## 常用命令

```
gitbook init: 初始化目录
gitbook build: 编译
gitbook serve: 在线预览
```

gitbook serve命令在windows平台下经常出错，使用gulpfile.js代替

```js
var browserSync = require('browser-sync').create()
var reload = browserSync.reload
var gulp = require('gulp')
var gitbook = require('gitbook')
var path = require('path')
var del = require('del')


// path of your *.md book files
var rootPath = path.join(__dirname)

// output path where generated *.html will be stored
var outputPath = path.join(rootPath, '_book')

// gulp.watch instance
var watcher


// rebuild book + start server
gulp.task('default', function (done) {
  rebuildBook(function () {
    browserSync.init({
      server: {
        baseDir: outputPath
      }
    })
    done()
  })
})


// kill watcher + remove/clean output dir + build book
function rebuildBook (done) {

  // pause watcher while building book progress
  if (watcher) {
    watcher.end()
    watcher = undefined;
  }

  // ensure output path is not exists otherwise book won't generated
  return del(path.join(outputPath)).then(paths => {
    buildBook().then(function ()
      // start watcher after built
      startWatch().on('ready', function(){
        done();
      }).on('error', function(e){
        console.error('ERROR: watch error... $s', e)
      })
    })
  })
}


// build book
function buildBook () {
  var fs = gitbook.createNodeFS(rootPath)
  var book = gitbook.Book.createForFS(fs)
  var Parse = gitbook.Parse
  var Output = gitbook.Output
  var Generator = Output.getGenerator('website')

  return Parse.parseBook(book)
    .then(function (resultBook) {
      return Output.generate(Generator, resultBook, {
        root: outputPath
      })
    })
}


// start watching md files + when files changed reload browser
function startWatch() {
  var rp = path.join(rootPath, '/**/*.md')
  watcher = gulp.watch([rp, '!' + rp + '/_book/' ], function () {
    rebuildBook(reload)
  })
  return watcher;
}
```