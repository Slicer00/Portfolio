---
title: GitHub ActionsでAstroを選択してビルド失敗するときの対処法
published: 2025-04-01
description:  pnpmをGitHub Actionsで使い、Pagesにデプロイする
image: "./cover.png"
tags: [Markdown, Blogging]
category: Blogging
draft: false
---

## 問題の概要

Astroを使用してプロジェクトを構築し、GitHub Actionsを利用してPagesにデプロイしようとする際にAstroを選択するとビルドエラーが発生する。

```
Error: Cannot find module 'pnpm'
```

このエラーは、自動生成される　`.github\workflows\astro.yml` でpnpmではなくnpmがインストールされ、依存関係が不足していることが原因。
また上記画像の手順でastroをworkflowに設定してしまうとdependabotが動かなくなる。

## 解決方法
### 手順1: `package-lock.json`をコミットしていることを確認

プロジェクトのルートディレクトリに`package-lock.json`が存在することを確認し、Gitにコミットされているか確認。以下のコマンドを使用して確認できる。

```bash
git ls-files | grep package-lock.json
```

もし`package-lock.json`がコミットされていない場合は`.gitignore`に含まれていないか確認してコミット。

### 手順2: Astro公式DOCのymlファイルを置く

[AstroサイトをGitHub Pagesにデプロイする](https://docs.astro.build/ja/guides/deploy/github/)の`yml`ファイルをコピペして `.github\workflows\deploy.yml`として配置、存在するastro.ymlファイルは削除する。


これによってビルド開始時にdependabotが動いていれば成功。

pnpmの環境がGitHub Actionsのキャッシュに保存される。