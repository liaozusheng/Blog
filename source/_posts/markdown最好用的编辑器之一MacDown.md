title: "markdown最好用的编辑器之一MacDown"
date: 2015-05-17 11:13:18
categories: 技术
tags: 
 - markdown
 - hexo 
 - macdown
---
#前言

Hexo博客是markdown语法，就是我们熟悉的md后缀，经常上github，或是iOS项目README都是使用md的，当时我也不知道，以为就是类似于txt格式的文本文件。在hexo的教程里面都说Sublime Text是支持markdown语法的，实际上就只是代码高亮。其实真正的问题在于markdown语法很严格（特别是空格），在编辑博客的时候经常发生一些细节的小问题，而且每次要生成在本地跑一次预览一下，然后再修改，再生成，再预览……很是麻烦。所以急需一款可以实时预览的编辑器。
![MacDown Screenshot](http://d.pr/i/10UGP+)
<!--more-->
##MacDown
估计有很多人会在MacDown和Mou谁更好用产生不同的意见，确实Mou是先行者，MacDown在某系方面是有借鉴Mou的，0到1和1到100差距无疑是巨大的。但是作为使用者，其实没必要去考虑哪个更好用。只要用得习惯，操作顺手就行。而MacDown作者Chung的一句话也表明了他的立场。
> Let’s focus on making better software for everyone.

欣喜的是，目前两款软件都找到自己的发展模式，Mou 已经完成了众筹，MacDown 依旧会走自己开源的道路。

MacDown的下载和使用也是非常简单的，在[MacDown官网](http://macdown.uranusjr.com/)就可以下载，有win和Mac版本。我使用的Mac版本。从官网的介绍可以看出来，MacDown的作者对Mou还是保持了相当尊重的态度，也承认了Mark的地位。但是作者在MarkDown上面还是添加了自己需要的新特性。
```
	Highly customisable Markdown rendering.
	Syntax highlighting in fenced code blocks.
	Sophisticated auto-completion.
```
在安装完成后第一次打开，有一个README文档，里面详细的介绍了MacDown的特性以及语法功能等。下面是我摘抄里面的一段。



## <a name="markdown-pane"></a>The Markdown Preference Pane
This is where I keep all preferences related to how I parse markdown into html.  
![Markdown preferences pane](http://d.pr/i/RQEi+)

### Document Formatting
The ***Smartypants*** extension automatically transforms straight quotes (`"` and `'`) in your text into typographer’s quotes (`“`, `”`, `‘`, and `’`) according to the context. Very useful if you’re a typography freak like I am. Quote and Smartypants are syntactically incompatible. If both are enabled, Quote takes precedence.


### Block Formatting

#### Table

This is a table:

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

You can align cell contents with syntax like this:

| Left Aligned  | Center Aligned  | Right Aligned |
|:------------- |:---------------:| -------------:|
| col 3 is      | some wordy text |         $1600 |
| col 2 is      | centered        |           $12 |
| zebra stripes | are neat        |            $1 |

The left- and right-most pipes (`|`) are only aesthetic, and can be omitted. The spaces don’t matter, either. Alignment depends solely on `:` marks.

#### <a name="fenced-code-block">Fenced Code Block</a>

This is a fenced code block:

```
print ('Hello world!)'
```

You can also use waves (`~`) instead of back ticks (`` ` ``):

~~~
print('Hello world!')
~~~


You can add an optional language ID at the end of the first line. The language ID will only be used to highlight the code inside if you tick the ***Enable highlighting in code blocks*** option. This is what happens if you enable it:

![Syntax highlighting example](http://d.pr/i/9HM6+)

I support many popular languages as well as some generic syntax descriptions that can be used if your language of choice is not supported. See [relevant sections on the official site](http://macdown.uranusjr.com/features/) for a full list of supported syntaxes.


### Inline Formatting

The following is a list of optional inline markups supported:

Option name         | Markup           | Result if enabled     |
--------------------|------------------|-----------------------|
Intra-word emphasis | So A\*maz\*ing   | So A<em>maz</em>ing   |
Strikethrough       | \~~Much wow\~~   | <del>Much wow</del>   |
Underline [^under]  | \_So doge\_      | <u>So doge</u>        |
Quote [^quote]      | \"Such editor\"  | <q>Such editor</q>    |
Highlight           | \==So good\==    | <mark>So good</mark>  |
Superscript         | hoge\^(fuga)     | hoge<sup>fuga</sup>   |
Autolink            | http://t.co      | <http://t.co>         |
Footnotes           | [\^4] and [\^4]: | [^4] and footnote 4   |

[^4]: You don't have to use a number. Arbitrary things like `[^footy note4]` and `[^footy note4]:` will also work. But they will *render* as numbered footnotes. Also, no need to keep your footnotes in order, I will sort out the order for you so they appear in the same order they were referenced in the text body. You can even keep some footnotes near where you referenced them, and collect others at the bottom of the file in the traditional place for footnotes. 



