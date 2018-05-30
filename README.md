# xiabibi-cactus

> 本主题 fork 自 cactus 主题，[项目主页](https://github.com/probberechts/hexo-theme-cactus)。主题最新版请从原作者处下载，本主题仅做风格上的修改和部分 bug 修复。
> `fork`版本：3.0

## 说明

主题默认修改为**白色**，其中所有的修改也是基于**白色主题**修改的，在其他颜色方案上未做测试。

[主题演示](https://blog.mrcxt.com/)

[自定义标签演示](https://blog.mrcxt.com/2018/04/12/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A0%87%E7%AD%BE/)

## 更新

*   の
    *   修复部分 bug
*   の
    *   添加搜索页面
*   の
    *   添加 分类页 和 标签页,可在 主题配置 文件中的 nav 选项中控制
*   の
    *   修改 bash 命令行样式
*   の
    *   添加 live2d 控件
    *   增添部分样式
    *   增添`danger类`警告窗样式
*   の
    *   解决无法添加文章列表页的 bug
    *   ~~新添标签云页面~~
*   の
    *   修改`code`代码块样式
    *   分离`pre`代码块样式
    *   添加`highlight`高亮方案`avue.css`,样式为 vue 官网风格

------------------------------------ 我是分割线 ------------------------------------

## 安装

1.  下载主题文件:

    ```git
    $ git clone https://github.com/Mrcxt/xiabibi-cactus.git
    ```

2.  将主题文件放入`themes`文件夹中

3.  在`config.yml`中修改`theme`.

    ```yml
    # theme: landscape
    theme: xiabibi-cactus
    ```

4.  运行命令`hexo server -d`查看效果吧

## 关于 live2d

具体配置请参照 [live2d 项目](https://github.com/EYHN/hexo-helper-live2d)

## 配置

你可以修改`_config.yml`文件来自定义配置

注意：这里有两种方式来修改。hexo 下的`_config.yml`和主题下的`_config.yml`，前者将覆盖后者的变量。

For example:

```yml
# _config.yml
theme_config:
  colorscheme: white
```

```yml
# themes/cactus/_config.yml
colorscheme: dark
```

这将导致主题为白色

你也可以创建新的颜色方案`source/css/_colors`.

### 导航栏

Setup the navigation menu in the `_config.yml`:

```yml
nav:
  Home: /
  About: /about/
  Writing: /archives/
  Projects: URL
  LINK_NAME: URL
```

### 首页文章列表

你可以决定显示多少条文章在你的首页

*   只显示最近的 10 条内容

    ```yml
    posts_overview:
      show_all_posts: false
      post_count: 10
    ```

*   显示全部文章

    ```yml
    posts_overview:
      show_all_posts: true
    ```

### 项目列表

可以通过自`source/_data/projects.json`来展示项目列表，注意是 hexo 下的 source 文件夹，而非主题文件下。

```json
[
    {
        "name": "Hexo",
        "url": "https://hexo.io/",
        "desc": "A fast, simple & powerful blog framework"
    },
    {
        "name": "Font Awesome",
        "url": "http://fontawesome.io/",
        "desc": "The iconic font and CSS toolkit"
    }
]
```

### 社交媒体链接

Cactus can automatically add links to your social media accounts.
Therefore, update the theme's `_config.yml`:

```yml
social_links:
  github: your-github-url
  twitter: your-twitter-url
  NAME: your-NAME-url
```

where `NAME` is the name of a [Font Awesome icon](https://fontawesome.com/icons?d=gallery&s=brands).

### 语言

If you are new to Hexo and internationalization (i18n), please read
[Hexo documentation - internationalization (i18n) section](https://hexo.io/docs/internationalization.html)

Currently, the theme is delivered with support for:

*   English (en), default
*   Chinese (Simplified, PRC) (zh-CN)
*   Dutch (nl)
*   French (fr)
*   Persian (fa)
*   Russian (ru)
*   Spanish (es)

If you would like to use one the languages listed above, simply set `language`
to the desired language (e.g., `fr`) in `_config.yml`.
Otherwise, you can follow the steps below (E.g., to add a Japanese (ja) translation):

1.  Set `language` to `ja` in Hexo configuration file `_config.yml`
2.  Create a `ja.yml` file in the `themes/cactus/languages/` folder
3.  Copy the content of `themes/cactus/languages/default.yml` and paste it it into the `ja.yml` file
4.  Replace all English strings by their Japanese translation

**Note: Cactus does not support multi-language sites.**

### RSS

Set the `rss` field in the `_config.yml` to one of the following values:

1.  `rss: false` will totally disable rss (default).
2.  `rss: atom.xml` sets a specific feed link.
3.  `rss:`leave empty to use the [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) plugin.

### Analytics

Add you Google Analytics or Baidu Tongji `tracking_id` to the `_config.yml`.

```yml
google_analytics:
  enabled: true
  id: 'UA-49627206-1'

baidu_analytics:
  enabled: true
  id: 2e6da3c375c8a87f5b664cea6d4cb29c
```

### 评论

First, create a site on Disqus: [https://disqus.com/admin/create/](http://disqus.com/admin/create/).

Next, update the `_config.yml` file:

```yml
disqus:
  enabled: true
  shortname: SITENAME
```

where `SITENAME` is the name you gave your site on Disqus.

### 代码高亮

Pick one of [the available colorschemes](https://github.com/probberechts/hexo-theme-cactus/tree/master/source/css/_highlight) and add it to the `_config.yml`:

```yml
highlight: COLORSCHEME_NAME
```

### 本地搜索

First, install the [hexo-generate-search](https://www.npmjs.com/package/hexo-generator-search)
plugin, which will generate a search index file.

```git
$ npm install hexo-generator-search --save
```

Next, create a page to display the search engine:

```sh
$ hexo new page Search
```

and put `search: true` in the front-matter.

Finally, edit the `_config.yml` and add a link to the navigation menu.

```yml
nav:
  search: /Search/
```

## License

MIT
