# 第4节:gitbook托管及生成文件

### 本地预览

在命令行输入：

```
gitbook serve
```

默认地址为： [http://localhost:4000](http://localhost:4000/)

serve 命令也可以指定端口：

```
$ gitbook serve --port 2333
```



### 生成电子书

在命令行输入：

```
gitbook build
```

build 命令可以指定路径：

```
gitbook build [书籍路径] [输出路径]
```



### 托管到 Github Pages
也许你以前也了解 Github 的一个功能： GitHub Pages 。它允许用户在 GitHub 仓库托管你的个人、组织或项目的静态页面（自动识别 html、css、javascript）。

#### 建立 xxx.github.io 仓库

要使用这个特性，首先，你必须建立一个严格遵循以下命名要求的仓库：Github账号名.github.io举例，我的 Github 账号为 atlantis1024，则这个仓库应该叫 atlantis1024.github.io。通常，这个仓库被用来作为个人或组织的博客。

#### 建立 gh-pages 分支

完成第1步后，在任意一个 Github 仓库中建立一个名为 gh-pages 的分支。只要 gh-pages 中的内容符合一个静态站点要求，就可以在如下地址中进行访问：https://Github用户名.gitbooks.io/Github 仓库 。例如：我的一个 Github 仓库名为 react-notes，则访问路径是：https://atlantis1024.github.io/react-notes

#### 自动化发布到 gh-pages

如果每次都手动 git push 到远程 gh-pages 分支，略有点麻烦。

怎么实现自动化发布呢？

有两种方法：

* 使用 gh-pages 插件

如果你了解 Nodejs，那么最简单的发布方式就是使用 gh-pages 插件。

先在本地安装插件

```
npm i -D gh-pages
```


然后，在 package.json 文件中添加脚本命令：

如下：-d 命令参数后面是要发布的静态站点内容的目录

```
"scripts": {
  "deploy": "gh-pages -d build"
},
```

* 脚本

写一个执行 git 命令的脚本就搞定了。

下面的脚本无论是在 bat 或 sh 脚本中都可以执行。

```
cd build
git init
git checkout -b gh-pages
git add .
git commit -am "Update"
git push git@github.com:atlantis1024/gitbook-notes gh-pages --force"
```

