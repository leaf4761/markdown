# markdown 兼容 html
Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是 HTML 或是 Markdown。
# 特殊字符自动转换
在 HTML 文件中，有两个字符需要特殊处理：< 和 &
# 区块元素
markdown段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行
# 1.标题
### 第一种 stext模式
利用=和-放在文本下作为顶级和二级标题：  

    大标题
    ====
    副标题
    ---

效果图如下：
>
> 大标题
> ====
>
> 副标题
> ---

## 第二种 atx模式
前端的#数量 对应1-6级标题， #须与文本隔一个空格：

    # 这是 H1
    ## 这是 H2
    ###### 这是 H6
效果如下：
> # 这是 H1
> ## 这是 H2
> ###### 这是 H6
# 2.区块引用
### a.每行前加上>，或者在第一行前加上>,与文本隔一个空格

代码如下：

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
效果如下：

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

### b.区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 >

代码如下：

    > This is the first level of quoting.
    >
    > > This is nested blockquote.
    >
    > Back to the first level.
效果如下：
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

### c.引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等

代码如下：

    > ## 这是一个标题。
    > 
    > 1.   这是第一行列表项。
    > 2.   这是第二行列表项。
    > 
    > 给出一些例子代码：
    > 
    >     return shell_exec("echo $input | $markdown_script");
效果如下：
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");
# 3.列表
Markdown 支持有序列表和无序列表。

### 无序列表使用*、+或-作为列表标记：

    *   Red
    *   Green
    *   Blue
效果：
> *   Red
> *   Green
> *   Blue

### 有序列表则使用数字接着一个英文句点，与文本隔一个空格，最多 3 个空格，不过项目标记后面则一定要接着至少一个空格或制表符。可以不用在意数字的正确性，输出的结果与输入顺序一致：

    1. Bird
    3. McHale
    2. Parish

    <ol>
    <li>Bird</li>
    <li>McHale</li>
    <li>Parish</li>
    </ol>
效果：
> 1. Bird
> 3. McHale
> 2. Parish
> 
> <ol>
> <li>Bird</li>
> <li>McHale</li>
> <li>Parish</li>
> </ol>
### 列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符：
代码：

    1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

    2.  Suspendisse id sem consectetuer libero luctus adipiscing. 
效果：
> 1.  This is a list item with two paragraphs. Lorem ipsum dolor
>     sit amet, consectetuer adipiscing elit. Aliquam hendrerit
>     mi posuere lectus.
> 
>     Vestibulum enim wisi, viverra nec, fringilla in, laoreet
>     vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
>     sit amet velit.
> 
> 2.  Suspendisse id sem consectetuer libero luctus adipiscing.

如果要在列表项目内放进引用，那 > 就需要缩进：

代码：

    * A list item with a blockquote:

        > This is a blockquote
        > inside a list item.
效果：
> * A list item with a blockquote:
> 
>     > This is a blockquote
>     > inside a list item.

### 如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符：

代码：

    *   一列表项包含一个列表区块：

            <代码写在这>
效果：
> *   一列表项包含一个列表区块：
> 
>         <代码写在这>

正常记录，若在行首出现数字-句点-空白，可以在句点前面加上反斜杠，避免识别为列表：

代码：

    1986\. What a great season.

效果：
> 1986\. What a great season.
# 4.代码区块
### 要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以

代码：

    这是一个普通段落：

        这是一个代码区块。

效果：

> 这是一个普通段落：
> 
>     这是一个代码区块。

一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。在代码区块里面， & 、 < 和 > 会自动转成 HTML 实体，这样的方式可以非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要复制贴上，再加上缩进就可以了。

代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号

# 5.分割线
可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

    * * *
    ***
    *****
    - - -
    ---------------------------------------

效果：
> * * *
> ***
> *****
> - - -
> ---------------------------------------

# 区段元素
# 1.链接
Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。

不管是哪一种，链接文字都是用 [方括号] 来标记，链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写，下面两个链接是一样的：

    [link text][a]
    [link text][A]

### 行内式
要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可

    This is [an example](http://example.com/ "Title") inline link.

    [This link](http://example.net/) has no title attribute.

效果：
> This is [an example](http://example.com/ "Title") inline link.
>
> [This link](http://example.net/) has no title attribute.

如果是要链接到同样主机的资源，可以使用相对路径：

代码：

    See my [About](/about/) page for details.
效果：
> See my [About](/about/) page for details.

### 参考式
参考式的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记。

接着，在文件的任意处，你可以把这个标记的链接内容定义出来.

代码：

    This is [an example][id] reference-style link.
    [id]: http://example.com/  "Optional Title Here"
效果：
> This is [an example][id] reference-style link.
>
> [id]: http://example.com/  "Optional Title Here"

链接内容定义的形式为：

    方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
    接着一个冒号
    接着一个以上的空格或制表符
    接着链接的网址
    选择性地接着 title 内容，可以用单引号、双引号或是括弧包着
下面三种写法一致：

    [foo]: http://example.com/  "Optional Title Here"
    [foo]: http://example.com/  'Optional Title Here'
    [foo]: http://example.com/  (Optional Title Here)

### 隐式链接标记功能让可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果要让 "Google" 链接到 google.com：

    [Google][]
    [Google]: http://google.com/

代码：

    Visit [Daring Fireball][] for more information.
    [Daring Fireball]: http://daringfireball.net/

效果：
> Visit [Daring Fireball][] for more information.
>
> [Daring Fireball]: http://daringfireball.net/

# 2.强调
Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 * 或 _ 包围的字词会被转成用`<em>`标签包围，用两个 * 或 _ 包起来的话，则会被转成`<strong>`，例如：

    *single asterisks*
    _single underscores_
    **double asterisks**
    __double underscores__
效果：
> *single asterisks*
>
> _single underscores_
>
> **double asterisks**
>
> __double underscores__

强调也可以直接插在文字中间：

    un*frigging*believable
效果：
> un*frigging*believable

如果 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。

如果要在文字前后直接插入普通的星号或底线，可以用反斜线转义

# 3.代码
### 如果要标记一小段行内代码，可以用反引号把它包起来（`），代码：

    Use the `printf()` function.
效果：
> Use the `printf()` function.

### 如果要在代码区段内插入反引号，可以用多个反引号来开启和结束代码区段，代码：

    ``There is a literal backtick (`) here.``
效果：
> ``There is a literal backtick (`) here.``

### 代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样就可以在区段的一开始就插入反引号，代码：

    A backtick-delimited string in a code span: `` `foo` ``
效果：
> A backtick-delimited string in a code span: `` `foo` ``

Please don't use any `<blink>` tags

### 在代码区段内，& 和方括号都会被自动地转成 HTML 实体，这使得插入 HTML 原始码变得很容易，代码：

    Please don't use any `<blink>` tags.
效果：
> Please don't use any `<blink>` tags.

# 4.图片
Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

Markdown 还没有办法指定图片的宽高，需要的话，可以使用普通的 <img> 标签。

### 行内式的图片语法

    ![Alt text](/path/to/img.jpg)
    ![Alt text](/path/to/img.jpg "Optional title")
    详细叙述如下：
    a.一个惊叹号 !
    b.接着一个方括号，里面放上图片的替代文字
    c.接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

### 参考式的图片语法

    ![Alt text][id]
    [id]: url/to/image  "Optional title attribute"

# 其他

### 自动链接

Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成链接，代码：

    <http://example.com/>
    <address@example.com>
效果：
> <http://example.com/>
>
> <address@example.com>

### 反斜杠

Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号
例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 `<em>` 标签），可以在星号的前面加上反斜杠：

    \*literal asterisks\*
效果：
> \*literal asterisks\*

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

    \   反斜线
    `   反引号
    *   星号
    _   底线
    {}  花括号
    []  方括号
    ()  括弧
    #   井字号
    +   加号
    -   减号
    .   英文句点
    !   惊叹号

参考文章 <https://www.appinn.com/markdown/>