---
title: "Zoom Marketplace AppのShared access permissionsがAuthorizedされてるか確認する方法"
emoji: "🌊"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Zoom", "marketplace", "OAuth", "app", "API"]
published: true
---

Zoom MarketpalceのOAuth AppでShared access permissionsがAuthorizedされているのか事前にチェックしたいと思って調べてみました。

# 結論 

## Shared access permissionsがAuthorizedされてるか確認するAPIはないとのこと

>Currently, **there is no way** for your app to know whether a user has authorized shared access permissions for your app.

[Shared access permissions](https://developers.zoom.us/docs/api/rest/using-zoom-apis/#shared-access-permissions)


# 対策

Forumでいくつかリクエスとが上がっているようなので、今後APIができる可能性があるのかもしれませんが今のところ確認するAPIはないとのことです。

テストでミーティングを作成を試みてチェックするしかないかと思います。
ミーティング作成に失敗したらShared access permissionsがAuthorizedされていない可能性があるので、
Authorizedされているのか確認とAuthorizedの手順を案内して対応しようと思います。


## そもそもアプリが追加されているかの確認

ミーティングのリストを取得するAPIでエラーが返ってきたらアプリが追加されていないものと判断できるずです。
```
GET /users/{userId}/meetings
```
[List meetings](https://developers.zoom.us/docs/api/rest/reference/zoom-api/methods/#operation/meetings)
