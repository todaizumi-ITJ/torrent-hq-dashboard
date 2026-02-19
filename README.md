# 司令部ダッシュボード — AI Management

軍隊式指揮系統に基づくマルチユニット経営ダッシュボード。

## URL

- **メイン**: https://todaizumi-itj.github.io/torrent-hq-dashboard/
- **旧HQ（ディスカッション詳細）**: https://todaizumi-itj.github.io/torrent-hq-dashboard/old-hq.html

## タブ構成

| タブ | 内容 |
|---|---|
| 全体概況 | 総兵力・日報提出率・アラート・ユニット別状況 |
| ユニット一覧 | 全ユニットのカード表示（定員・ステータス） |
| ユニットA〜 | ユニットごとの詳細（メンバー・タスク・エスカレーション） |
| 通信状況 | 質問・回答・指示・エスカレーションのログ |
| ディスカッション | エージェント間のディスカッション一覧 |
| タイムライン | 今日の活動時系列 |

## スケーラビリティ

- `DATA.units` 配列にユニットを追加するだけで自動的にタブ・カード・詳細ページが生成される
- 1ユニット最大7人、ユニット数は無制限
- AI参謀が `unit-hub-*` / `executive-hub` リポジトリからデータを取得し `DATA` オブジェクトを更新

## データ更新フロー

```
unit-hub-a (git) → executive-hub AI → DATA オブジェクト更新 → StaticCrypt暗号化 → GitHub Pages
unit-hub-b (git) ↗
```

## ファイル構成

- `index.html` — 司令部ダッシュボード（メイン）
- `old-hq.html` — 旧Torrent HQ ディスカッションダッシュボード（StaticCrypt暗号化済み）
