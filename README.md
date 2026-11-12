# Time Hub

時計・カレンダー・タイマー・ストップウォッチを1画面にまとめた、iPad(横向き)向けのPWAです。

- 左上: デジタル時計(タイムゾーン切り替え)
- 右半分: カレンダー(日付ごとのメモ)
- 左下: タイマー / ストップウォッチ

依存ライブラリなしの静的ファイルのみ(`index.html`, `sw.js`, `manifest.webmanifest`, `icons/`)。
HTTPSで配信し、iPad の Safari から「ホーム画面に追加」で使います。

## Lite版

`simple/` 配下は時計を時:分のみ・大きく表示し、ストップウォッチを外した簡易版です(`simple/index.html`, `simple/sw.js`)。標準版と同じオリジンで公開され、Service Worker のキャッシュ名は標準版が `timehub-v*`、Lite版が `timehub-lite-v*` です。それぞれ自分の系列の古いキャッシュだけを削除します。

## 更新について

- 配信は network-first(通信できるときは常に最新を取得)なので、`index.html` などの内容変更だけならキャッシュ名の更新は不要です。
- キャッシュ名(`sw.js` の `CACHE`)を上げるのは、プリキャッシュするファイル一覧を変えたときなどに限ります。
- 公開URL: https://idbem9-tdy.github.io/time-hub/ (標準版)、https://idbem9-tdy.github.io/time-hub/simple/ (Lite版)。リポジトリ名から導いたURLです
