

# 前端开发规范


> 在多人协作的团队里，需要制定一套合理的规范，才会让开发更加方便、统一。

```
一、命名规则
    1. 项目命名
    2. 目录命名
    3. 文件命名
二、HTML
    1. HTML5 Doctype
    2. lang 属性
    3. 字符编码
    4. IE 渲染模式
    5. 引入 CSS、JS
    6. 属性顺序
三、CSS
    1. 命名
    2. 书写顺序
    3. 颜色简写
    4. SCSS相关
四、JavaScript
    1. 命名
    2. 引号
    3. 注释
    4. 缩进
    5. 分号
五、Vue相关规范
    1. 组件标签
    2. *.vue文件规范
        template
        script
六、结尾
```

### 一、命名规则

命名使用 `-` 号作为连接符

#### 1. 项目命名

根据项目域名来创建项目，如下：
 
    applease.zhaoliangji.com - 项目1
    erpmarketing.zhaoliangji.com - 项目2

#### 2. 目录命名

    app, app-h5

#### 3. 文件命名

- css 文件

    普通文件：
        
        app.css、my-home.css
        
    自定义插件：
        
        假设项目组 w 使用 'w-' 开头：w-form.css、w-page.css 等。
        假设项目组 b 使用 'b-' 开头：b-form.css、b-page.css 等。

- js 文件

    普通文件：
        
        app.js、my-home.js
        
    自定义插件：
        
        假设项目组 w 使用 'w-' 开头：w-form.js、w-page.js 等。
        假设项目组 b 使用 'b-' 开头：b-form.js、b-page.js 等。

- html 文件

        .order.html、order-pay.html

注：其它文件也遵循以上规则。

### 二、HTML

#### 1. HTML5 Doctype

在页面开头使用这个简单地 doctype 来启用标准模式，使其在每个浏览器中尽可能一致的展现；虽然 doctype 不区分大小写，但是按照惯例，doctype 大写。

```
<!DOCTYPE html>
<html>
    ...
</html>
```

#### 2. lang 属性

根据 HTML5 规范：应在 html 标签上加上 lang 属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。

```
<!DOCTYPE html>
<html lang="zh">
    ...
</html>
```

#### 3. 字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为'UTF-8'。

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    ...
</html>
```

#### 4. IE 渲染模式

用 `<meta>` 标签可以指定页面应该用什么版本的IE来渲染。

```
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
    ...
</html>
```
注：Edge 表示 IE 最新的版本模式，也可以等于 IE=9、IE=8 等。

#### 5. 引入 CSS、JS

根据 HTML5 规范, 通常在引入 CSS 和 JS 时不需要指明 `type` ，因为 `text/css` 和 `text/javascript` 分别是他们的默认值。

```
<!-- 一引入CSS -->
<link rel="stylesheet" href="order-pay.css">

<!-- 文档中 CSS -->
<style>
    ...
</style>

<!-- 引入JS -->
<script src="order-pay.js"></script>

<!-- 文档中 JS -->
<script>
    ...
</script>
```

#### 6. 属性顺序

属性应该按照特定的顺序出现以保证易读性。

- class
- id
- name
- data-*
- src, for, type, href, value , max-length, max, min, pattern
- placeholder, title, alt
- aria-*, role
- required, readonly, disabled

class 是为高可复用组件设计的，所以应处在第一位；
id 更加具体且应该尽量少使用，所以将它放在第二位。

```
<i class="icon icon-menu" id="menu" data-toggle="tooltip" title="菜单"></i>

<input class="form-control" type="text">

<img src="..." alt="...">
```

### 三、CSS

#### 1. 命名

使用减号拼接

```
/* not good */
.head__top{
    color: #ABCDEF;
    background-color: #001122;
}

/* good */
.head-top{
    color: #ABCDEF;
    background-color: #001122;
}

/* not good */
#headTop{
    color: #ABCDEF;
    background-color: #001122;
}

/* good */
#head-top{
    color: #ABCDEF;
    background-color: #001122;
}
```

#### 2. 书写顺序

- 位置属性 (position, top, right, z-index, display, float 等)
- 大小 (width, height, padding, margin)
- 文字系列 (font, line-height, letter-spacing, color- text-align 等)
- 背景 (background, border 等)
- 其他 (animation, transition 等)

#### 3. 颜色简写

颜色16进制用小写字母
颜色16进制尽量用简写

```
/* not good */
.head-top{
    color: #ABCDEF;
    background-color: #001122;
}

/* good */
.head-top{
    color: #abcdef;
    background-color: #012;
}
```

#### 4. SCSS相关

```
/* not good */
@import "_dialog.scss";

/* good */
@import "dialog";

/* not good */
.fatal {
    @extend .error;
}

/* good */
.fatal {
    @extend %error;
}

/* not good */
.element {
    & > .dialog {
        ...
    }
}

/* good */
.element {
    > .dialog {
        ...
    }
}
```
嵌套方式
```
.v-btn{
    display: inline-block;
    padding: 6px 20px;
    font-size: 14px;
    line-height: 20px;
    background: $defaultBg;
    color: $defaultColor;
    white-space: nowrap;
    border-radius: 3px;
    border: none;
    outline: none;
    cursor: pointer;
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
    &-default{
        @include button-define($defaultBg, 'btn');
        &.is-border {
            @include button-border-define($defaultBg, 'default');
        }
    }
}
```

### 四、JavaScript

#### 1. 命名

- 标准变量采用驼峰式命名
- 私有变量必须以“_”开头命名
- 构造函数首字母必须大写
- jQuery 对象必须以 “$” 开头命名

```
/* 基本变量 */
var thisIsMyName;

/* 私有变量 */
var _name = 'Jone';

/* 构造函数 */
function Person(name) {
    this.name = name;
}

/* jQuery对象 */
var $orderBox = $('body') ;
```

#### 2. 引号

最外层统一使用单引号

```
var _name = 'Jone',
    _html = '<div class="one"></div>';
```

#### 3. 注释

- 单行注释

```
if (action === 'set') {
    // 发送信息
    sendMsg();
}
```

- 多行注释

```
/* jQuery对象 */
var $orderBox = $('body') ;
```

- 文档注释

```
/**
 * 倒计时
 * @param el        - 元素
 * @param seconds   - 秒数
 * @param startText - 倒计时中文案
 * @param endText   - 结束后文案
 * @param callback  - 结束后回调方法
 */
function countDown(options) {
    var vm = this;
    var defaults = {
        seconds: 60,
        startText: '${seconds}s',
        endText: '重发验证码',
        callback: function () {
        }
    };
    options = Object.assign({}, defaults, options);

    if (!options.el) return;
    if (vm.countDown.status) return;
    vm.countDown.status = true;
    options.el.innerHTML = options.startText.replace('${seconds}', options.seconds);

    var time = null;
    time = setInterval(function () {
        options.seconds--;
        if (!options.seconds) {
            clearInterval(time);
            options.el.innerHTML = defaults.endText;
            vm.countDown.status = false;
            options.callback ? options.callback() : '';
            return;
        }
        options.el.innerHTML = options.startText.replace('${seconds}', options.seconds);
    }, 1000);
}
```

#### 4. 缩进

统一4个缩进

```
var x = 1,
    y = 1;

if (x < y) {
    x += 10;
} else {
    x += 1;
}
```

#### 5. 分号

每个语句后面必须加分号

```
/* var declaration */
var x = 1;

/* expression statement */
x++;

/* do-while */
do {
    x++;
} while (x < 10);
```

### 五、Vue相关规范

#### 1. 组件标签

标签以 `-` 拼接命名，比如引入一个按钮：
```
<v-button>默认</v-button>
<v-button type="primary">主要</v-button>
```

#### 2. *.vue文件规范

##### template

属性最外层使用双引号，如：

```
// good
<div class="app-container">

// bad
<div class='app-container'>
```
##### script

使用单引号，如：

```
// good
import {Component, Vue} from 'vue-property-decorator';

// bad
import {Component, Vue} from "vue-property-decorator";
```

    
### 六、结尾

本规范可能写的不是很完善，如有好的建议欢迎提出。