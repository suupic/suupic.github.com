---
layout: post
title: "IE下的trim()"
description: ""
category: development 
tags: [ie, trim, 前端]
---
{% include JB/setup %}

IE没有实现JS的trim()方法，遇到trim()会报错"Object doesn't support this property or method"

有两种解决方法：

1. 给string增加trim方法
```javascript
if(typeof String.prototype.trim !== 'function') {
  String.prototype.trim = function() {
    return this.replace(/^\s+|\s+$/g, ''); 
  }
}
```

2. 用JQuery的trim()函数
