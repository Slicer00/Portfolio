---
title: SoundCloud上にアップロードした音楽をMarkdownに埋め込む
published: 2025-04-01
description: 音楽を埋め込む例
tags: [Example, DTM]
category: Examples
draft: false
---

## 音楽を埋め込む例

以下は、SoundCloud上にアップロードした音楽ファイルをMarkdownに埋め込んだ例です。

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1947356611&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/slicer00" title="すらいさー" target="_blank" style="color: #cccccc; text-decoration: none;">すらいさー</a> · <a href="https://soundcloud.com/slicer00/ancient-lost-memories" title="Ancient Lost Memories" target="_blank" style="color: #cccccc; text-decoration: none;">Ancient Lost Memories</a></div>

具体的には

1. SoundCloudに音楽をアップロード
    - SoundCloudアカウントを作成、音楽ファイルをアップロード

2. アップロードした音楽の共有リンクを取得
    - 音楽のページに移動し、「共有」ボタンをクリック
    - 「埋め込み」タブを選択し、埋め込みコードをコピー

3. コピーした埋め込みコードをMarkdownファイルに貼り付け
    - 上記の例のように、`<iframe>`タグを使用して埋め込み

4. 必要に応じて、埋め込みコードのパラメータを調整

:::tip
例: `auto_play=false` を `auto_play=true` に変更すると、自動再生が有効
:::

5. Markdownファイルを保存し、サイトをビルドまたはプレビューして埋め込みが正しく表示されることを確認します。