# Starter Trader

Hyperliquidの無期限先物向けに、Pythonで注文を出すプログラムです。銘柄や注文分割数、エントリー・利確条件、ポジションのタイムアウトなどを設定できます。スポット取引には対応していません。

## 使っているもの

- Python、pandas、NumPy
- Hyperliquid Python SDK
- Google Cloud Functions v2、Cloud Scheduler

## ローカルで動かす

設定方法と必要な環境変数は[実装ディレクトリのREADME](starter-trader/README.md)にまとめています。

```bash
cd starter-trader
make install
make run
```

実装は `starter-trader/main.py`、注文やログの補助処理は `starter-trader/localpackage/` にあります。APIキーなどの認証情報はローカルで管理し、Gitには追加しないでください。

無期限先物の注文を出すコードなので、設定と対象アカウントを確認してから実行してください。関連する記事は[Starter Trader](https://blog.shidokamo.com/starter-trader)です。
