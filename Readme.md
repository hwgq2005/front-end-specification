前端开发规范

V1.0

1. 命名规则        3

1) 项目命名        3

2) 目录命名        3

3) 文件命名        3

2. HTML        4

1) HTML5 Doctype        4

2) lang属性        4

3) 字符编码        4

4) IE渲染模式        5

5) 引入CSS、JS        5

6) 属性顺序        5

3. CSS        6

1) 命名        6

2) 书写顺序        7

3) 颜色简写        7

4. JavaScript        7

1) 命名        7

2) 引号        8

3) 注释        8

5. SEO优化        9

6. 开发工具        11

1) 编辑器        11

2) jQuery Api 在线文档        11

3) 前端构建工具        11

4) css sprite        11







1.
# 1.命名规则

1. 1)项目命名

tronker,soffice,app-tronker,app-soffice

1. 2)目录命名

js, css, images, my-page

1. 3)文件命名
  1. css文件：

- .普通文件：

app.css,my-home.css

- .自定义插件：

Tronker使用 &#39;t-&#39; 开头：t-form、t-page等。

Sofiice使用 &#39;s-&#39; 开头：s-form、s-page等。

1.
  1. js文件：

- .普通文件：

app.js,my-home.js

- .自定义插件：

Tronker使用&#39;t-&#39; 开头：t-form、t-page等。

Sofiice使用 &#39;s-&#39; 开头：s-form、s-page等。

1.
  1. html文件:order.html,order-pay.html

其它文件也遵循以上规则。

1. 2.HTML

1. 1)HTML5 Doctype

在页面开头使用这个简单地doctype来启用标准模式，使其在每个浏览器中尽可能一致的展现；虽然doctype不区分大小写，但是按照惯例，doctype大写。

&lt;!DOCTYPE html&gt;

&lt;html&gt;

        ...

&lt;/html&gt;

1. 2) **lang属性**

根据HTML5规范：应在html标签上加上lang属性。这会给语音工具和翻译工具帮助，告诉它们应当怎么去发音和翻译。

&lt;!DOCTYPE html&gt;

&lt;htmllang=&quot;zh&quot;&gt;

        ...

&lt;/html&gt;

1. 3)字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为&#39;UTF-8&#39;。

&lt;!DOCTYPE html&gt;

&lt;html&gt;

    &lt;head&gt;

        &lt;metacharset=&quot;UTF-8&quot;&gt;

    &lt;/head&gt;

        ...

&lt;/html&gt;

1. 4)IE渲染模式

用 &lt;meta&gt; 标签可以指定页面应该用什么版本的IE来渲染；

&lt;!DOCTYPE html&gt;

&lt;html&gt;

    &lt;head&gt;

        &lt;metahttp-equiv=&quot;X-UA-Compatible&quot;content=&quot;IE=Edge&quot;&gt;

    &lt;/head&gt;

        ...

&lt;/html&gt;

注：Edge表示IE最新的版本模式，也可以等于IE=9、IE=8等。

1. 5)引入CSS、JS

根据HTML5规范, 通常在引入CSS和JS时不需要指明 type，因为 text/css 和text/javascript 分别是他们的默认值。

&lt;!-- 一引入CSS --&gt;

&lt;linkrel=&quot;stylesheet&quot;href=&quot;order-pay.css&quot;&gt;

&lt;!-- 文档中CSS --&gt;

&lt;style&gt;

        ...

&lt;/style&gt;

&lt;!-- 引入JS --&gt;

&lt;script src=&quot;order-pay.js&quot;&gt;&lt;/script&gt;

&lt;!-- 文档中JS --&gt;

&lt;script&gt;

        ...

&lt;/script&gt;

1. 6)属性顺序

属性应该按照特定的顺序出现以保证易读性；

- .class
- .id
- .name
- .data-\*
- .src, for, type, href, value , max-length, max, min, pattern
- .placeholder, title, alt
- .aria-\*, role
- .required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。

&lt;iclass=&quot;icon icon-menu&quot;id=&quot;menu&quot;data-toggle=&quot;tooltip&quot;title=&quot;菜单&quot;&gt;&lt;/i&gt;

&lt;inputclass=&quot;form-control&quot;type=&quot;text&quot;&gt;

&lt;imgsrc=&quot;...&quot;alt=&quot;...&quot;&gt;

1. 3.CSS

1. 1)命名

使用减号拼接

/\* not good \*/

.head\_\_top{

    color:#ABCDEF;

background-color:#001122;

}

/\* good \*/

.head-top{

    color:#ABCDEF;

background-color:#001122;

}

/\* not good \*/

#headTop{

    color:#ABCDEF;

background-color:#001122;

}

/\* good \*/

#head-top{

    color:#ABCDEF;

background-color:#001122;

}

1. 2)书写顺序

1. 1．位置属性(position, top, right, z-index, display, float等)
2. 2．大小(width, height, padding, margin)
3. 3．文字系列(font, line-height, letter-spacing, color- text-align等)
4. 4．背景(background, border等)
5. 5．其他(animation, transition等)

1. 3)颜色简写

颜色16进制用小写字母

颜色16进制尽量用简写

/\* not good \*/

.head-top{

    color:#ABCDEF;

background-color:#001122;

}

/\* good \*/

.head-top{

    color:#abcdef;

background-color:#012;

}

1. 4.JavaScript

1. 1)命名

1. 1．标准变量采用驼峰式命名
2. 2．私有变量必须以&quot;\_&quot;开头命名
3. 3．构造函数首字母必须大写
4. 4．jQuery对象必须以&quot;$&quot;开头命名

/\* 基本变量\*/

varthisIsMyName;

/\* 私有变量\*/

var\_name = &#39;Jone&#39;;

/\* 构造函数\*/

     functionPerson(name){

        this.name=name;

 }

/\* jQuery对象\*/

     var$orderBox = $(&#39;body&#39;) ;



1. 2)引号

最外层统一使用单引号

var\_name = &#39;Jone&#39;;

     var\_html = &#39;&lt;div class=&quot;one&quot;&gt;&lt;/div&gt;&#39;;

1. 3)注释

1. 1．单行注释

if(action === &#39;set&#39;){

    // 发送信息

    sendMsg();

}

1. 2．多行注释

/\* jQuery对象\*/

     var$orderBox = $(&#39;body&#39;) ;

1. 3．文档注释

/\*\*

\* 一个带参数的函数

\* @param {string}   type - 类型

\* @param {number} time - 毫秒

\*/

functionfoo(type,time){

        ...

}

1. 5.SEO优化

SEO（Search Engine Optimization）就是搜索引擎优化，是指为了增加网页在搜索引擎自然搜索结果中的收录数量以及提升排序位置而做的优化行为。

一、HTML标签权重分值排列

内部链接文字：10分

标题title：10分

域名：7分

H1，H2字号标题：5分

每段首句：5分

路径或文件名：4分

相似度（关键词堆积）：4分

每句开头：1.5分

加粗或斜体：1分

文本用法（内容）：1分

title属性：1分（注意不是&lt;title&gt;，是title属性，比如a href=… title=&quot;）

alt标记：0.5分

Meta描述（Description属性）：0.5分

Meta关键词（Keywords属性）：0.05分

1. 二、优化方法

作为一名前端，我们不需要精通SEO，但我们需要去了解它。以下就以前端这块来说下如何提升SEO的方法：

1. 1)简化代码结构，更利于搜索引擎分析抓取有用内容

页面尽量采用DIV+CSS，当然，表格展现模式用table还是比div方便很多的；所有js、css采用外联方式，图片采用css精灵，减少请求次数。

1. 2)每个页面只能出现一次H1标签，H2标签可以多次

H1权重很高，普遍认为仅次于title，一般资讯详情页的标题、商品详情页的标题，都放在H1里。

1. 3)Meta标签的优化

Title：突出重点，不出现重复关键字，关键字排前，每个页面的title都要不同。

Description：把页面的内容概括在这里，长度要合理。

Keywords：列表出几个关键字即可。

1. 4)为图片添加alt、title描述

&lt;imgsrc=&quot;images/logo.png&quot;alt=&quot;logo&quot; title=&quot;这是一个logo&quot;&gt;

1. 5)避免表格的嵌套

1. 6)采用web标准进行网站重构

1. 7)FLASH应用

FLASH由于不含文字信息，应尽量用于功能展示和广告，少用于网站栏目和页面。

1. 8)尽少使用iframe框架

搜索引擎不会抓取到iframe里的内容，重要内容不要放在框架中。

1. 9)资讯的内部链接

有助提高网站排名和PR值，例如相关资讯、推荐资讯等。

1. 6.开发工具

1. 1)编辑器


1. 1．sublime

下载地址： [http://www.sublimetext.com/3](http://www.sublimetext.com/3)

主题安装： [http://www.itbulu.com/20-sublime-themes.html](http://www.itbulu.com/20-sublime-themes.html)

1. 2)jQuery Api 在线文档

地址： [http://www.css88.com/jqapi-1.9](http://www.css88.com/jqapi-1.9)

1. 3)前端构建工具

Gulp： [http://www.gulpjs.com.cn/](http://www.gulpjs.com.cn/)

Grunt：http://www.gruntjs.net/

1. 4)css sprite

在线地址： [http://www.spritecow.com](http://www.spritecow.com/)