# 第1节: gitbook安装

- gitbook介绍

  - GitBook 是使用 GitHub / Git 和 Markdown（或AsciiDoc）构建漂亮书籍的命令行工具（和Node.js库）。

  - GitBook 可以将您的内容作为网站（可定制和可扩展）或电子书（PDF，ePub或Mobi）输出。

  - GitBook.com 是使用 GitBook 格式创建和托管图书的在线平台。它提供托管，协作功能和易于使用的编辑器。

- node的安装

  - 打开 <https://nodejs.org/> 点击绿色的 INSTALL 按钮下载安装 node，npm会随着安装包一起安装。	

  - nodejs 镜像配置
    国内的，我推荐大家使用阿里巴巴的镜像地址 http://registry.npm.taobao.org 。执行下面的命令，进行配置。

    ##### npm config set registry http://registry.npm.taobao.org

  - 可以在终端输入
    - node -v
    - 查看node的版本号 同样输入
    - npm -v 
    - 查看npm的版本号

  - 如果以上都出现，步骤没有出错，接下来就可以安装gitbook了。

- gitbook的安装

  - npm install gitbook-cli -g 

- 初始化项目

  - 创建目录，切换到目录下，执行：gitbook init 

  - 会发现目录下面多了2个文件，**README.md**和**SUMMARY.md**。还可以设置book.json和Glossary.md 。

    | 文件        | 描述                              |
    | ----------- | --------------------------------- |
    | book.json   | 配置数据 (**optional**)           |
    | README.md   | 电子书的前言或简介 (**required**) |
    | SUMMARY.md  | 电子书目录 (**optional**)         |
    | GLOSSARY.md | 词汇/注释术语列表 (**optional**)  |



    - README.md 和 SUMMARY.md 是两个必须文件
      - README.md 是对书籍的简单介绍
      - SUMMARY.md 是书籍的目录结构
        - 执行 gitbook init 会根据 SUMMARY.md 目录生成对应的文件夹和 md 文件，每一个 md 文件对应每一章节，每一章节的内容在对应的 md 文件里编辑。
        - 如果想要新增章节，可以在 SUMMARY.md 里面新增，然后执行 gitbook init 就会新增对应的 md 文件，原有文件不会变化；
        - 如果想要删除章节，在 SUMMARY.md 里面删除，然后执行 gitbook init 想要删除的 md 文件并不会删除，需要手动删除。