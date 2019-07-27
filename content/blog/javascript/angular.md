---
title: Angular.js的用法
date: 2015-08-23
author: 阮一峰
---

Angular的典型句法之一。

```html
<div ng-bind=”username” ></div>
```

## 模板

```html

<ul> 
    <li ng-repeat="framework in frameworks" title="{{framework.description}}">               
                  {{framework.name}} 
    </li> 
</ul>

```

## 双向绑定

```html

<input ng-model="user.name" type="text" />
Hello {{user.name}}!

```
