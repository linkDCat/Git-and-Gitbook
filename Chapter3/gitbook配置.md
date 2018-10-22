# 第2节: gitbook配置



### 静态文件和图片

静态文件是在 SUMMARY.md 中未列出的文件。除非被忽略，否则所有静态文件都将复制到输出路径。



### 忽略文件和文件夹

GitBook将读取 .gitignore，.bookignore 和 .ignore 文件，以获取要过滤的文件和文件夹。这些文件中的格式遵循 .gitignore 的规则：

```
# This is a comment

# Ignore the file test.md

test.md

# Ignore everything in the directory "bin"

bin/*
```



### book.json常规设置

```
GitBook 允许您使用灵活的配置自定义您的电子书。这些选项在 book.json 文件中指定。
```



| 变量        | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| root        | 包含所有图书文件的根文件夹的路径，除了 `book.json`           |
| structure   | 指定自述文件，摘要，词汇表等的路径，参考 [Structure paragraph](https://blog.csdn.net/stu059074244/article/details/77767835#structure). |
| title       | 您的书名，默认值是从 README 中提取出来的。在 GitBook.com 上，这个字段是预填的。 |
| description | 您的书籍的描述，默认值是从 README 中提取出来的。在 GitBook.com 上，这个字段是预填的。 |
| author      | 作者名。在GitBook.com上，这个字段是预填的。                  |
| isbn        | 国际标准书号 ISBN                                            |
| language    | 本书的语言类型 —— [ISO code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) 。默认值是 `en` |
| direction   | 文本阅读顺序。可以是 `rtl` （从右向左）或 `ltr` （从左向右），默认值依赖于 `language` 的值。 |
| gitbook     | 应该使用的GitBook版本。使用 [SemVer](http://semver.org/) 规范，并接受类似于 `“> = 3.0.0”` 的条件。 |



### author

作者姓名，在GitBook.com上，这个字段是预先填写的。

例：

```json
"author" : "victor zhang"
```



### description

电子书的描述，默认值是从 README 中提取出来的。在GitBook.com上，这个字段是预先填写的。

例：

```
"description" : "Gitbook 教程"
```



### direction

文本的方向。可以是 rtl 或 ltr，默认值取决于语言的值。

例：

```
"direction" : "ltr"
```



### gitbook

应该使用的GitBook版本。使用SemVer规范，接受类似于 >=3.0.0 的条件。

例：

```
"gitbook" : "3.0.0",
"gitbook" : ">=3.0.0"
```



### language

Gitbook使用的语言, 版本2.6.4中可选的语言如下：

```
en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw
```


例：

```
"language" : "zh-hans",
links
```



在左侧导航栏添加链接信息

例：

```
"links" : {
    "sidebar" : {
        "Home" : "https://github.com/atlantis1024/gitbook-notes"
    }
}
```



### root

包含所有图书文件的根文件夹的路径， book.json 文件除外。

例：

```
"root" : "./docs",
```



### structure

指定 Readme、Summary、Glossary 和 Languages 对应的文件名。

这些文件必须在项目的根目录下（或 root 的根目录，如果你在 book.json 中配置了 root 属性）。不接受的路径，如：dir / MY_README.md。​	

| 变量                | 描述                                     |
| ------------------- | ---------------------------------------- |
| structure.readme    | Readme 文件名（默认值是  README.md ）    |
| structure.summary   | Summary 文件名（默认值是 SUMMARY.md ）   |
| structure.glossary  | Glossary 文件名（默认值是 GLOSSARY.md ） |
| structure.languages | Languages 文件名（默认值是 LANGS.md ）   |



### styles

自定义页面样式， 默认情况下各generator对应的css文件

例：

```
"styles": {
    "website": "styles/website.css",
    "ebook": "styles/ebook.css",
    "pdf": "styles/pdf.css",
    "mobi": "styles/mobi.css",
    "epub": "styles/epub.css"
}
```


例如要使 h1、h2 标签有下边框， 可以在 website.css 中设置

```
h1 , h2{
    border-bottom: 1px solid #EFEAEA;
}
```



### title

电子书的书名，默认值是从 README 中提取出来的。在 GitBook.com 上，这个字段是预先填写的。

例：

```
"title" : "gitbook-notes",
```

