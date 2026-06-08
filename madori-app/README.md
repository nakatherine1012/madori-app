# 間取り3Dビューア — デプロイ手順

## ファイル構成
```
madori-app/
├── public/
│   └── index.html        ← メインアプリ
├── netlify/
│   └── functions/
│       └── claude.js     ← Claude API プロキシ
└── netlify.toml          ← Netlify設定
```

## Netlifyデプロイ手順

1. このフォルダをZIPで固める（またはGitHubにpush）
2. netlify.com → "Add new site" → "Deploy manually"
3. ZIPをドラッグ＆ドロップ
4. デプロイ後、**Site settings → Environment variables** で以下を追加：
   ```
   ANTHROPIC_API_KEY = sk-ant-xxxxxxx
   ```
5. **Deploys → Trigger deploy** で再デプロイ

## 機能
- 手書き図面アップロード → Claude Vision で自動解析 → 3D反映
- チャットで修正指示 → 間取りデータ更新 → 2D/3D即時反映
- 図面画像をチャットに添付して「この通りに修正して」も可能
- 1〜3階タブ切り替え、分割/2D/3D表示切替
- 910mmグリッド、部屋クリックで寸法表示
