<img src="https://cdn.jsdelivr.net/gh/D-Sketon/hugo-theme-reimu@main/images/screenshot.png"/>
<div align = center>
  <h1>hugo-theme-reimu</h1>
  <img alt="version" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhugo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">
  <img alt="GitHub License" src="https://img.shields.io/github/license/D-Sketon/hugo-theme-reimu">
  <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/D-Sketon/hugo-theme-reimu">
  <p align="center">
  💘 博麗 霊夢 💘
  </p>

[演示网站](https://d-sketon.github.io/hugo-theme-reimu) | [迁移指南](https://d-sketon.github.io/20241110/hexo-to-hugo-guide/)

简体中文 | [English](https://github.com/D-Sketon/hugo-theme-reimu/blob/main/README.en.md)

</div>

A Hakurei Reimu style Hugo theme. Migrated from [hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu).

---

|framework|repository|version|stars|
|-|-|-|-|
|[Hexo](https://hexo.io/)|[hexo-theme-reimu](https://github.com/D-Sketon/hexo-theme-reimu)|<img alt="version" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhexo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">|<img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/D-Sketon/hexo-theme-reimu">|
|[Astro](https://astro.build)|[astro-theme-reimu](https://github.com/D-Sketon/astro-theme-reimu)|<img alt="version" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fastro-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">|<img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/D-Sketon/astro-theme-reimu">|
|[Hugo](https://gohugo.io)|[hugo-theme-reimu](https://github.com/D-Sketon/hugo-theme-reimu)|<img alt="version" src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fgithub.com%2FD-Sketon%2Fhugo-theme-reimu%2Fraw%2Fmain%2Fpackage.json&query=%24.version&label=version">|<img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/D-Sketon/hugo-theme-reimu">|

**项目刚刚开始，欢迎提出 Issue 和 PR！**

## 特性

- 所有的博客常规功能
- 兼容 Hugo 0.116.0 及以上版本
- 响应式布局
- 代码高亮，代码粘贴
- KaTeX / MathJax3 展示数学公式
- Mermaid 展示流程图
- Algolia 搜索
- valine / waline / twikoo / gitalk / giscus 评论系统
- valine / waline 文章阅读统计
- 不蒜子访客统计
- RSS
- 同时支持 iconfont 和 fontawesome
- 黑夜模式
- 图片懒加载
- 加载动画
- TOC
- 鼠标动画
- pjax
- ServiceWorker
- live2d / live2d-widgets
- reimu 鼠标指针
- 内部提供内链/外链/友链卡片的短代码
- 文章底部版权声明
- 配置自定义 CDN 源
- Aplayer / Meting 音乐播放器
- 高度自定义

## 安装

```bash
cd themes
git clone --single-branch --branch main https://github.com/D-Sketon/hugo-theme-reimu.git
```

并修改 `hugo.toml` 中的 theme

```toml
theme = 'hugo-theme-reimu'
```

## 使用

<details>
<summary>创建配置</summary>

### 创建配置

#### 主题配置

在外层 `config` 文件夹下创建 `_default` 文件夹，然后将主题内的 `config/_default/params.yml` 复制到 `_default` 文件夹下，此文件作为主题配置文件，可在此文件中修改主题配置

#### 数据配置

将主题内的 `config/data/` 文件夹内的所有文件复制到外层 `data` 文件夹下，此文件夹内的文件用于配置主题内的数据：

- `covers.yml` 用于配置随机封面图片
- `friends.yml` 用于配置友链
- `vendor.yml` 用于配置第三方库的 CDN 源

#### 静态资源配置

主题的静态资源（favicon，头图等）位于 `static` 文件夹内，你可以在外层 `static` 文件夹下创建相应的文件夹，然后将主题内的文件复制到外层文件夹下，以覆盖主题内的默认文件

> 总之一句话，不建议直接修改主题内的文件，而是在外层创建相应的文件夹，然后将主题内的文件复制到外层文件夹下，以覆盖主题内的默认文件，这样便于主题升级

#### 语言配置

reimu 支持多语言。如果你想要使用中文，请在 `hugo.toml` 中添加如下配置

```toml
languageCode = 'zh-CN'
defaultContentLanguage = 'zh-CN'
[languages]
[languages.zh-CN]
languageName = '简体中文'
weight = 1
```

</details>
<details>

<summary>基本结构</summary>

### 基本结构

为了保证显示正确，请参考 `_example` 在 `content` 中建立 `archives` 和 `post` 文件夹 （里面的 `_index.md` 不可省略，且注意 `post` 的 `draft` 为 `true`）

#### archives

- `_index.md` 用于显示归档页面，不可省略

#### post

文章请在此目录下创建，注意 `draft` 为 `true` 的文章不会显示在首页

- `_index.md` 用于忽略 `post/index.html` 的生成，不可省略

#### about\.md

关于页面

#### friend\.md

友链页面

</details>
<details>
<summary>封面、头图和图标</summary>

### 封面、头图和favicon

#### 封面

随机封面图片请参考主题内的 `data/covers.yml` 文件结构，在外层 `data` 文件夹下创建 `covers.yml` 文件，格式如下：

```yaml
- https://example.com/1.jpg
- https://example.com/2.jpg
```

封面显示逻辑如下

- 如果文章的 Front matter 中包含 cover 的 url，则该文章头图和首页缩略图均显示该 url

```yaml
---
title: Hello World
cover: https://example.com
---
```

- 如果文章的 Front matter 中包含 cover 为 `false`，则该文章不显示头图（首页上仍然是随机图片）

```yaml
---
title: Hello World
cover: false
---
```

- 如果文章的 Front matter 中包含 cover 为 `rgb(xxx,xxx,xxx)`，则该文章头图为对应的渐变纯色（首页上仍然是随机图片）

```yaml
---
title: Hello World
cover: rgb(255,117,117)
---
```

- 否则查找 `data` 文件夹中的 `covers.yml`，并从中随机挑选图片
- 若上述文件均不存在，则显示头图

#### 头图

头图保存于 `themes/hugo-theme-reimu/static/images/banner.webp`，可在 `params.yml` 中修改路径和名字

```yaml
banner: "images/banner.webp"
```

#### favicon

favicon 保存于 `themes/hugo-theme-reimu/static/favicon.ico`，可自行覆盖替换

</details>
<details>
<summary>代码块</summary>

### 代码块

为保证代码块的正确显示，请保证 `hugo.toml` 中有如下配置

```toml
[markup.highlight]
guessSyntax = true
noClasses = false
```

代码块同时提供了代码粘贴功能，点击代码块右上角的复制按钮即可复制代码。在 `params.yml` 中可以对复制功能进行配置。  
`success` 为复制成功时的提示，`fail` 为复制失败时的提示。此外，可以配置版权声明，当复制的字符数大于 `count` 时会在复制的内容后面添加 `content` 版权声明。

```yaml
clipboard:
  success: 复制成功(*^▽^*)
  fail: 复制失败 (ﾟ⊿ﾟ)ﾂ
  copyright:
    enable: false
    count: 50 # 大于多少字符添加版权声明
    content: 本文版权：本博客所有文章除特别声明外，均采用 BY-NC-SA 许可协议。转载请注明出处！
```

v0.2.0 添加了配置用于控制代码块的默认展开状态，`expand` 可以设置为 `true`、`false` 或数字，数字表示当代码块的行数大于该数字时默认收缩。

```yaml
code_block:
  expand: true # true | false | number
```

</details>
<details>
<summary>站内评论</summary>

### 站内评论

> 站内评论可以使用 Front matter 中的 `comments` 独立控制每篇文章是否显示评论。  
> 当 `comments` 为 `false` 时不显示评论，`true` 或不填时根据 `params.yml` 的配置决定是否显示。

若基于 [Valine](https://valine.js.org/)  
请参考其官方文档完成 `LeanCloud` 的配置，并在 `params.yml` 中将 `valine.enable` 改为 `true`，并填入自己的 `appId` 和 `appKey`

```yaml
valine:
  enable: true
  appId: "your appId"
  appKey: "your appKey"
```

若基于 [Waline](https://waline.js.org/)  
请参考其[官方文档](https://waline.js.org/guide/get-started/)完成 `LeanCloud` 的配置，并在 `params.yml` 中将 `waline.enable` 改为 `true`，并填入自己的 `serverURL`

```yaml
waline:
  enable: true
  serverURL: "your server url"
  lang: zh-CN
  locale: {} # https://waline.js.org/guide/features/i18n.html#%E8%87%AA%E5%AE%9A%E4%B9%89%E8%AF%AD%E8%A8%80
  emoji:
    - https://unpkg.com/@waline/emojis@1.2.0/weibo
    - https://unpkg.com/@waline/emojis@1.2.0/alus
    - https://unpkg.com/@waline/emojis@1.2.0/bilibili
    - https://unpkg.com/@waline/emojis@1.2.0/qq
    - https://unpkg.com/@waline/emojis@1.2.0/tieba
    - https://unpkg.com/@waline/emojis@1.2.0/tw-emoji
  meta:
    - nick
    - mail
    - link
  requiredMeta:
    - nick
    - mail
  wordLimit: 0
  pageSize: 10
  pageview: true
```

若基于 [twikoo](https://twikoo.js.org)  
请参考其[官方文档](https://twikoo.js.org/quick-start.html)完成 腾讯云 或 Vercel 部署，并在 `params.yml` 中将 `twikoo.enable` 改为 `true`，并填入自己的 `envId`

```yml
twikoo:
  enable: true
  envId: # 腾讯云环境填 envId；Vercel 环境填地址（https://xxx.vercel.app）
  region:
```

若基于 [giscus](https://giscus.app/zh-CN)，请参考文档完成仓库的配置，并在 `params.yml` 中将 `giscus.enable` 改为 `true`，并填入对应的数据

```yml
giscus:
  enable: true
  repo: "your repo"
  repoId: "your repoId"
  category: "your category"
  categoryId: "your categoryId"
  mapping: mapping
  strict: 0
  reactionsEnabled: 1
  emitMetadata: 0
  inputPosition: bottom
  # commentTheme: preferred_color_scheme invalid
  lang: zh-CN
```

若基于 [gitalk](https://gitalk.github.io/)  
请参考其[官方文档](https://github.com/gitalk/gitalk?tab=readme-ov-file#usage)完成仓库的配置，并在 `params.yml` 中将 `gitalk.enable` 改为 `true`，并填入对应的数据

```yml
gitalk:
  enable: true
  clientID: "your application client ID"
  clientSecret: "your application client secret"
  repo: "your repo"
  owner: "repo owner"
  admin: "repo owner and collaborators"
  md5: false # 是否使用 md5 加密路径
```

</details>

<details>
<summary>站内搜索</summary>

### 站内搜索

基于 [Algolia](https://www.algolia.com/)，请在外层 `hugo.toml` 中添加如下配置

```toml
[outputs]
home = ["Algolia", "HTML", "RSS"]

[outputFormats.Algolia]
baseName = "algolia"
isPlainText = true
mediaType = "application/json"
notAlternative = true
```

这样会在 `public` 文件夹下生成 `algolia.json` 文件，用于 Algolia 搜索。接着你可以使用诸如 `atomic-algolia` 等插件将其上传到 Algolia

同时，在 `params.yml` 中将 `algolia_search.enable` 改为 `true`，并填写相关信息（**注意！这里填写的是Search-Only Key，不允许填写Admin Key！！否则可能被攻击**）

```yaml
algolia_search:
  enable: true
```

</details>
<details>
<summary>数学公式</summary>

### 数学公式

请先在外层 `hugo.toml` 中添加如下配置

```toml
[markup.goldmark.extensions.passthrough]
enable = true
delimiters.block = [["\\[", "\\]"], ["$$", "$$"]]
delimiters.inline = [["\\(", "\\)"], ["$", "$"]]
```

并在需要使用数学公式的文章的 Front matter 中添加 `math` 为 `true`

```yaml
---
math: true
---
```

> 注意不要同时开启 KaTeX 和 MathJax3

#### KaTeX

若基于 [Katex](https://github.com/KaTeX/KaTeX)，请在 `params.yml` 中将 `math.katex.enable` 改为 `true`

```yaml
math:
  katex:
    enable: true
```

#### MathJax3

若基于 [MathJax3](https://www.mathjax.org/)，请在 `params.yml` 中将 `math.mathjax.enable` 改为 `true`，并可在 `options` 中添加配置（由于 Hugo 会自动将对象的key转变为全小写，所以配置需要放在一个数组中避免默认行为）

```yaml
math:
  mathjax:
    enable: true
    options: [{}]
```

</details>
<details>
<summary>Mermaid</summary>

### Mermaid

流程图基于 [Mermaid](https://mermaid.js.org/#/)，请在需要使用流程图的文章的 Front matter 中添加 `mermaid` 为 `true`

```yaml
---
mermaid: true
---
```

</details>
<details>
<summary>RSS</summary>

### RSS

RSS 自带，无需额外配置

</details>

<details>
<summary>Icon</summary>

### Icon

Icon 默认使用本项目提供的 iconfont

```yml
icon_font: 4552607_tq6stt6tcg
```

如果想要继续使用 fontawesome 图标，请将 `icon_font` 设置为 `false`，此时会使用 `vendor.yml` 中对应的 fontawesome

```yml
fontawesome:
  high_priority:
    - webcache|@fortawesome/fontawesome-free@6.5.1/css/regular.min.css
    - webcache|@fortawesome/fontawesome-free@6.5.1/css/solid.min.css
  low_priority:
    - webcache|@fortawesome/fontawesome-free@6.5.1/css/brands.min.css
    - webcache|@fortawesome/fontawesome-free@6.5.1/css/v5-font-face.min.css
    - webcache|@fortawesome/fontawesome-free@6.5.1/css/v4-font-face.min.css
```

</details>

<details>
<summary>高级功能</summary>

### 高级功能

#### Pace 进度条

默认开启

```yaml
pace:
  enable: true
```

#### firework

默认开启

```yaml
firework:
  enable: true
```

具体配置请查看 [mouse-firework](https://github.com/D-Sketon/mouse-firework)

#### pjax

默认关闭

```yaml
pjax:
  enable: false
```

> pjax 用于那些需要添加音乐播放器等需要 SPA 的用户。但其仍然属于实验性质，引入后可能会出现诸如**脚本无法执行**、**脚本重复执行**、**页面渲染混乱**等 BUG。请慎重考虑！

#### ServiceWorker

默认关闭

```yaml
service_worker:
  enable: false
```

#### live2d

默认关闭

```yaml
live2d:
  enable: false
  position: left # left | right
```

#### live2d-widgets

默认关闭

```yaml
live2d_widgets:
  enable: false
  position: left # left | right
```

#### reimu 鼠标指针

默认开启

```yml
reimu_cursor: true
```

#### 头图响应式

默认关闭，打开后并提供对应尺寸的图片和媒体查询可以在一定程度上提高移动端的 LCP

```yml
banner_srcset:
enable: false
srcset:
  - src: "images/banner-600w.webp"
    media: "(max-width: 479px)"
  - src: "images/banner-800w.webp"
    media: "(max-width: 799px)"
  - src: "images/banner.webp"
    media: "(min-width: 800px)"
```

#### quicklink

默认开启，打开后可以在用户停留在页面时预加载链接，提高用户体验

```yml
quicklink:
  enable: true
  timeout: 3000 # 预加载超时时间
  priority: true # 是否优先加载
  ignores: [] # 忽略的链接，仅支持字符串
```

#### 文章版权声明

默认关闭

```yml
article_copyright:
enable: false # 是否展示版权卡片？
content:
  author: # true | false 版权卡片展示作者？
  link: # true | false 版权卡片展示链接？
  title: # true | false 版权卡片展示标题？
  date: # true | false 版权卡片展示创建日期？
  updated: # true | false 版权卡片展示更新日期？
  license: # true | false 版权卡片展示协议？
```

此外，也可以通过文章的 front-matter 控制，其优先级高于全局配置

```yaml
---
copyright: true # 是否展示版权卡片？
---
```

#### 过期提醒

默认关闭

```yml
outdate:
  enable: false
  daysAgo: 180 # 多少天前的文章算过期
  message: 本文最后更新于 {time}，请注意文中内容可能已经发生变化。
```

#### 赞助

默认关闭

```yml
sponsor:
  enable: false # 是否展示赞助二维码？
  tip: 请作者喝杯咖啡吧！ # 赞助提示
  icon:
    url: "../images/taichi.png" # 赞助图标，相对于 css/style.css 的路径，所以需要向上一级才能找到 images 文件夹
    rotate: true # 是否旋转图标
    mask: true # 是否将图片作为遮罩（即只显示 png 图片的轮廓）
  qr:
    - name: 支付宝 # 二维码名称
      src: "sponsor/alipay.jpg" # 二维码路径，请自行填写
```

此外，也可以通过文章的 front-matter 控制，其优先级高于全局配置

```yaml
---
sponsor: true # 是否展示赞助二维码？
---
```

#### 音乐播放器（v0.4.0+）

> 使用前建议先打开 Pjax，否则会出现播放器自动暂停的问题

使用Aplayer + Meting（可选）默认关闭

##### 纯Aplayer

将 `player.aplayer.enable` 设置为 `true`，并在 `player.aplayer.options` 中参考 [Aplayer Docs](https://aplayer.js.org/#/home?id=options) 进行配置

```yml
player:
  aplayer:
    enable: true
    options:
      audio: [] # audio list
      fixed:
      autoplay:
      loop:
      order:
      preload: 
      volume:
      mutex:
      listFolded:
```

##### Aplayer + Meting

同时将 `player.aplayer.enable` 和 `player.meting.enable` 设置为 `true`，并在 `player.meting.options` 中参考 [Meting Docs](https://github.com/metowolf/MetingJS?tab=readme-ov-file#option) 进行配置，`player.aplayer.options` 为 Aplayer 配置

```yml
player:
  aplayer:
    enable: true
    options:
      audio: [] # this option will be overwritten by meting
      fixed:
      autoplay:
      loop:
      order:
      preload: 
      volume:
      mutex:
      listFolded:
  meting:
    enable: true
    meting_api: # custom api
    options:
      id: 
      server: 
      type: 
      auto:
```

</details>

<details>
<summary>内置卡片shortcode</summary>

### 内置卡片shortcode

#### friendLink 友链卡片

```yaml
{{< friendsLink >}}
```

无参数，直接读取 `data/friends.yml` 文件

#### postLinkCard 内链卡片

```yaml
{{<postLinkCard path="?" cover="?" escape="?" >}}
```

其中第一个参数为文章的 `path`；第二个参数（可选）为卡片展示的封面，如果设置为 `auto` 则自动使用博客的 `banner`；第三个参数（可选，`true | false`）表示文章标题是否被转义

#### externalLinkCard 外链卡片

```yaml
{{<externalLinkCard title="?" link="?" cover="?">}}
```

其中第一个参数为文章的标题；第二个参数为文章的外部链接，第三个参数（可选）为卡片展示的封面，如果设置为 `auto` 则自动使用缺省封面

</details>

<details>
<summary>自定义主题</summary>

#### 定制主题颜色

hugo-theme-reimu 主题支持通过 CSS 变量定制主题颜色，你可以通过修改 `:root` 伪类下的 CSS 变量来定制你的主题颜色。

变量文件位于 `assets/css/_variables.scss`，你可以在这个文件中找到所有的 CSS 变量，但其实只需要修改以下伪类下的变量即可：

```scss
:root {
  --red-0: hsl(0, 100%, 50%);
  --red-1: hsl(0, 100%, 66%);
  --red-2: hsl(0, 100%, 74%);
  --red-3: hsl(0, 100%, 84%);
  --red-4: hsl(0, 100%, 91%);
  --red-5: hsl(0, 100%, 95%);
  --red-5-5: hsl(0, 100%, 96%);
  --red-6: hsl(0, 100%, 98%);

  --color-red-6-shadow: hsla(0, 100%, 65%, 0.6);
  --color-red-3-shadow: hsla(0, 100%, 65%, 0.3);
}

[data-theme="dark"] {
  &:root {
    --red-4: hsla(0, 100%, 91%, 0.5);
    --red-5: hsla(0, 100%, 95%, 0.2);
    --red-5-5: hsla(0, 100%, 96%, 0.1);
    --red-6: hsla(0, 100%, 98%, 0.2);
  }
}
```

#### 自定义字体

可通过以下配置定义谷歌字体：

```yaml
# https://fonts.google.com/
font:
  article:
    - Mulish
    - Noto Serif SC
  code:
    # - Ubuntu Mono
    # - Source Code Pro
    # - JetBrains Mono
```

v0.2.0 添加了 `local_font` 配置用于定义本机字体，其优先级比谷歌字体低：

```yaml
local_font:
  article:
    - "-apple-system"
    - PingFang SC
    - Microsoft YaHei
    - sans-serif
  code:
    - Menlo
    - Monaco
    - Consolas
    - monospace
```

#### 定制图标

##### 头部 / 侧边栏图标

v0.1.0 的 `menu` 配置的结构发生了变化，允许用户自定义 icon。icon 为空时默认使用太极图标，你可以填写一个十六进制的数字来自定义 icon，同时支持 fontawesome 和 icon font。

```yaml
menu:
  - name: home
    url: /
    icon: # 不填默认使用太极图标
  - name: archives
    url: /archives
    icon: f0c1 # 你可以填写一个十六进制的数字来自定义 icon，支持 fontawesome 和 icon font
  - name: about
    url: /about
    icon:
  - name: friend
    url: /friend
    icon:
```

##### 底部 / 回到顶部 / 赞助图标

v0.1.0 的 `footer`、`top`、`sponsor` 配置均增加了 `icon` 配置用于自定义图标。

- `url` 为图标的路径，相对于 `css/style.css` 的路径，所以需要向上一级才能找到 images 文件夹。
- `rotate` 为是否旋转图标，默认为 `true`。
- `mask` 是否将图片作为遮罩（即只显示 png 图片的轮廓），默认为 `true`。

```yaml
footer:
  icon:
    url: "../images/taichi.png" # 相对于 css/style.css 的路径，所以需要向上一级才能找到 images 文件夹
    rotate: true
    mask: true

top:
  icon:
    url: "../images/taichi.png"
    rotate: true
    mask: true

sponsor:
  icon:
    url: "../images/taichi.png"
    rotate: true
    mask: true
```

##### 加载图标

v0.1.0 的 `preloader` 配置增加了 `icon` 配置用于自定义图标。icon 为空时默认使用内链的 svg（保证首屏加载速度），你可以填入一个链接来自定义加载图标。

不建议使用过大的图标，以免影响加载速度。

```yaml
preloader:
  enable: true
  text: 少女祈祷中...
  icon: # 不填默认使用内链的svg（保证首屏加载速度），你可以填入一个链接来自定义加载图标，如 '/images/taichi.png'
```

##### 锚点图标

v0.1.0 增加了 `anchor_icon` 配置用于自定义锚点图标，默认使用 `#` 图标，你可以填写一个十六进制的数字来自定义 icon，同时支持 fontawesome 和 icon font。

```yaml
anchor_icon: # 不填默认使用 # 图标
```

</details>

<details>
<summary>Vendor</summary>

### Vendor

目前 `vendor.yml` 中路径的组成方式为：`:cdn|:package@:version/:file`，`:cdn`可在 `vendor` 中自行配置。目前自带以下 CDN 源：

```yaml
cdn_jsdelivr_gh: https://cdn.jsdelivr.net/gh/ # 仅针对github加速
cdn_jsdelivr_npm: https://cdn.jsdelivr.net/npm/ # 仅针对npm加速
fastly_jsdelivr_gh: https://fastly.jsdelivr.net/gh/ # 仅针对github加速
fastly_jsdelivr_npm: https://fastly.jsdelivr.net/npm/ # 仅针对npm加速
unpkg: https://unpkg.com/ # 仅针对npm加速
webcache: https://npm.webcache.cn/ # 仅针对npm加速
```

用户可根据网络状况自行切换 CDN 源。
</details>

## 许可

MIT