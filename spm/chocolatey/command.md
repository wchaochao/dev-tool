# 命令

choco --help 查看帮助信息

```
Commands

 * list - lists remote or local packages
 * search - searches remote or local packages (alias for list)
 * info - retrieves package information. Shorthand for choco search pkgname --exact --verbose
 * install - installs packages from various sources
 * pin - suppress upgrades for a package
 * outdated - retrieves packages that are outdated. Similar to upgrade all --noop
 * upgrade - upgrades packages from various sources
 * uninstall - uninstalls a package
 * pack - packages up a nuspec to a compiled nupkg
 * push - pushes a compiled nupkg
 * new - generates files necessary for a chocolatey package from a template
 * sources - view and configure default sources (alias for source)
 * source - view and configure default sources
 * config - Retrieve and configure config file settings
 * feature - view and configure choco features
 * features - view and configure choco features (alias for feature)
 * apikey - retrieves or saves an apikey for a particular source
 * setapikey - retrieves or saves an apikey for a particular source (alias for apikey)
 * unpackself - have chocolatey set it self up
 * version - [DEPRECATED] will be removed in v1 - use `choco outdated` or `cup <pkg|all> -whatif` instead
 * update - [DEPRECATED] RESERVED for future use (you are looking for upgrade, these are not the droids you are looking for)
```

## 常用命令

* `choco search [package]`：远程搜索软件包
* `choco search [package] -a`：远程搜索软件包的所有版本
* `choco search [package] -l`：本地搜索软件包
* `choco search -la`：本地搜索全部软件
* `choco info [package] -l`：显示本地软件的详细信息
* `choco install [package1, package2...]`：安装一个或多个软件
* `choco install [package] --version [version]`：安装某个版本的软件
* `choco uninstall [package1, package2...]`：卸载一个或多个软件
* `choco uninstall [package] --version [version]`：卸载某个版本的软件
* `choco outdated`：显示需要更新的软件
* `choco upgrade [package1, package2...]`：更新一个或多个软件
* `choco upgrade all`：更新所有软件