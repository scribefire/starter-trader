# Starter Trader

Hyperliquidの無期限先物市場を対象にした、Python製の自動注文プログラムです。注文分割、価格条件、ポジションのタイムアウトなどを設定し、ローカル実行やGoogle Cloud Functions v2での実行を想定しています。

## 主な要素

- Hyperliquid Python SDKを使った取引所連携
- 銘柄、注文分割数、エントリー・利確条件、保有時間などの設定
- ログや注文処理をまとめた補助モジュール
- Google Cloud Functions v2へのデプロイとCloud Schedulerによる定期実行

このコードはスポット取引には対応していません。

## 技術スタック

- Python
- pandas、NumPy
- Hyperliquid Python SDK
- Google Cloud Functions、Cloud Scheduler（デプロイ構成）

## ローカル実行

詳細な設定手順と必要な環境変数は[実装ディレクトリのREADME](starter-trader/README.md)を参照してください。概要は次のとおりです。

```bash
cd starter-trader
make install
make run
```

API認証情報はローカルの設定ファイルで管理し、秘密鍵やAPIキーをGitに追加しないでください。クラウドへのデプロイ手順も実装ディレクトリのREADMEに記載されています。

## ディレクトリ

| パス | 内容 |
| --- | --- |
| `starter-trader/main.py` | 注文処理のエントリーポイント |
| `starter-trader/localpackage/` | 設定、ログ、注文関連の補助コード |
| `notebook/` | 検証用Notebook |

このリポジトリは実験・自動化のためのコードです。無期限先物には元本を失うリスクがあり、記載されたパラメーターや過去の分析は将来の成果を保証しません。関連する記事は[Starter Trader](https://blog.shidokamo.com/starter-trader)を参照してください。
