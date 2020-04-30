---
title: Hexo User Manual
permalink: Hexo-User-Manual
tags: [Hexo, NexT]
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Create a page

``` bash
$ hexo new page "tags"
```
### How to upgrade
```bash 
# 查看当前版本
$ hexo version

# 执行升级命令
$ npm update

# 查看升级后版本
$ hexo version
```
### Syntax

* Set multiple tags for a blog
```
tags: [tag1,tag2,tag3]
```

*  Insert html element to the page
``` 
layout: false
title: "个人简历"
---

<!doctype html>
<html lang="en">
<head>
...
```
