# Markdown
https://www.appinn.com/markdown/
## 概述
兼容html  特殊字符自动转换  转义字符表  

## 区块元素
### 段落和换行
换行：两个空格加enter或者&lt;br/&gt;
### 标题
类Setext: =或==加到标题底下  
类Atx形式：一到六级标题是1到6个#
### 区块引用
#### 整个段落加
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
#### 嵌套
> This is the first level of quoting.
> > This is nested blockquote.
### 列表
加*或+或-
* red
* blue
* green
### 代码区块
缩进4个空格或一个制表符，一个代码区块会一直持续到没有缩进的那一行  
这是一个普通段落：

    这是一个代码区块。
### 分隔线
三个星或线
* * *
***
*****
- - -
## 区块元素
### 链接
#### 行内式
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.  

See my [About](/about/) page for details.

#### 参考式
This is [an example][id] reference-style link.

[id]: http://example.com/  "Optional Title Here"
### 强调
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

只想显示符号： \*this text is surrounded by literal asterisks\*
### 代码
Use the `printf()` function.

``There is a literal backtick (`) here.``

A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``

### 图片

![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")

## 其他
### 自动链接
<http://example.com/>
### 反斜杠
\   反斜线`   反引号*   星号_   底线
{}  花括号
[]  方括号
()  括弧#   井字号+   加号-   减号
.   英文句点
!   惊叹号
