# [vui](https://brickies.github.io/vui/)

[![Version](https://img.shields.io/npm/v/x-vui.svg)](https://www.npmjs.com/package/x-vui) [![Downloads](http://img.shields.io/npm/dm/x-vui.svg)](https://www.npmjs.com/package/x-vui) [![License](https://img.shields.io/npm/l/x-vui.svg?style=flat)](https://opensource.org/licenses/MIT) [![TravisCI](https://travis-ci.org/Brickies/vui.svg)](https://travis-ci.org/Brickies/vui)

> It's a A personal Vue UI component library .

## 安装

### npm 安装

```shell
npm i yc-vui -S
```


## 快速开始

### 完整引入

```javascript
import Vue from 'vue'
import vui from 'yc-vui'
import 'yc-vui/lib/vui-css/index.css';

Vue.use(vui)
```

### 部分引入

```javascript
import Vue from 'vue'
import {
  Scroller,
  Select
  // ...
} from 'x-vui'
import 'x-vui/lib/vui-css/scroller.css';
import 'x-vui/lib/vui-css/select.css';

Vue.component(Scroller.name, Scroller)
Vue.component(Select.name, Select)
```

### 引入插件

**注：完整引入了vui，则无需再注册插件**

```javascript
import Vue from 'vue';
import { 
  $Toast, 
  $Dialog 
  // ...
} from 'x-vui';

Vue.prototype.$toast = $Toast
Vue.prototype.$dialog = $Dialog
```
