---
title: Github Actions + Hugo 自动更新 Algolia 索引
date: 2025-01-02T14:59:33+08:00
lastmod: 2025-01-03T01:29:33+08:00
tags:
  - hugo教程
categories:
  - hugo教程
---

首先，注册一个[Algolia](https://www.algolia.com/)账号，然后创建 `Search`一个 应用, 进入左下角的`Data sources` 依次点击`Crawler`→`Domains`绑定域名, 域名验证成功后可能创建一个`Crawler`, 不用管, 可以删掉它。  

在输出静态页面的 `Git` 项目的根目录下创建 `.github/workflows/algolia.yaml`文件, 参考 [文档](https://github.com/caibingcheng/hugo-algolia2) 和以下内容:

```yaml
name: deploy
on:
  push:
  workflow_dispatch:

jobs:
  generate-algolia:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: iChochy/Algolia-Upload-Records@main
        env:
         APPLICATION_ID: ${{ secrets.ALGOLIA_APP_ID }}
         ADMIN_API_KEY: ${{ secrets.ALGOLIA_API_KEY }}
         INDEX_NAME: ${{ secrets.ALGOLIA_INDEX_NAME }}
         FILE_PATH: "./algolia.json"
```

来到 [API Key](https://dashboard.algolia.com/account/api-keys?) 页面,

- 复制 `Application ID` 作为 `ALGOLIA_APP_ID`。  
- 复制 `Write API Key` 作为 `ALGOLIA_API_KEY`。

再来到 `Search` → `CONFIGURE` → `index` 

- 复制 `index` 下面的名字作为 `ALGOLIA_INDEX_NAME`。

  

在输出静态页面的GitHub仓库的 `Settings` → `Secrets and variables` → `Actions` 中新建 `Repository secrets` ,填入以上几个 `Secrets`。  



PS:如果在账号的 `Your plan and billing` 中发现没有 `CRAWLER` 的额度，说明 `Algolia` 官方的设置出了问题。我的方法是重新注册账号，选择 `Build` 套餐。
