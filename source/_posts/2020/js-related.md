---
title: js-related
permalink: js-related
date: 2020-05-04 19:24:21
tags: Javascript
categories: Javascript
---

### Js Related
1. disable inspect(development tools), right click
 看别人博客 想白嫖一下人家代码 发现人家博客禁用了inspect :(, Google了一下自己写了一个Demo
```html 
<body oncontextmenu="return false;">
</body>

// windows:  e.ctrlKey && e.shiftKey && e.keyCode === 'I'.charCodeAt(0)
// mac: e.altKey && e.metaKey && e.keyCode === 'I'.charCodeAt(0)
<script type="text/javascript">
  document.onkeydown = function(e) {
    if(event.keyCode === 123) {
      return false;
    }
    console.log(e.key);
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'I'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'C'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'J'.charCodeAt(0)) {
      return false;
    }
    if((e.ctrlKey || e.altKey) && (e.shiftKey || e.metaKey) && e.keyCode === 'U'.charCodeAt(0)) {
      return false;
    }
  }
</script>
```


