## 关于
把「幸福收藏夹」关了并没有后悔，只不过一直找不到合适的地方写点东西，特别是微博和朋友圈，
内容都特别碎，比较适合用来发些像「七月天的上海竟然可以如此冷」的状态。开公众号，发长微博，或者
在知乎写专栏都是可选择的途径，并且有那一句话「博客的精髓在于写，而不在于博客平台」，似乎不再
需要装个博客程序之类。可是，当一个人想写，又需要什么其他理由呢？虽然理由也有很多。

而这个仓库是一个静态网站生成器，基本流程就是：

```bash
## 开发，运行 file watch，可以直接写 ES6 / CSS Next / Jade
## 同时根据生成时间和内容，生产出文章列表 api
$ make dev

# 发布，生成静态文件，运行一个 build 服务器，在 GitHub 添加一个 webhook，
# 当一个 pull-request 被合并后会自动更新网站
$ make dist
```

## 写作
只要稍微配置一下 nginx 就可以访问整个网站了。而如果想写文章，把这生成器放在 GitHub，
开一个分支，在 `article/` 下开一个目录，直接开写 `jade`，完成后直接提交一个
`pull-request` 就可以了。合并后内容便会自动更新到网站了去。这种生成器和博客程序不同的是有
更多的权限，本来想把这程序叫做「Blogless」，因为她就专为程序员生的，没有限制的非博客。
直接写代码，想写什么就写什么，比如现在我写 ES6 和下一代 CSS 就完成可以直接写。
`jade` 也可以让我比简单的 HTML 更多的事，比如每篇都可以独立的布局，一个程序中的一篇文章
可以用 Angular.js，同时其他文章可以直接用 React 而又不冲突，每篇文章都像一个独立的 APP。

## 技术和工具
- Nginx：会做点简单的配置就可以了
- Node：运行一个服务来做自动更新，当然在 Nginx 中使用 lua 也可以执行 Script
- Gulp：静态生成基本就靠 gulp 来做整个流程，稍微要写点 Node 的东西，比如生成 API
- Makefile：直接使用 unix 命令行来做同步式流程
- Jade：最好的模板语言，也不想争辩，只能说太好用了

基本来说就是自由，自动。
