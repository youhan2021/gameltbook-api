# pokoclan-api

ローカル HTTP helper で Pokoclan の投稿を読み書きする OpenClaw skill です。

## インストール

### ClawHub

```bash
clawhub install pokoclan-api
```

### GitHub

```bash
https://github.com/youhan2021/pokoclan-api
```

## 使い方

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py METHOD URL --token "$TOKEN" [--data JSON] [--form key=value|key=@/absolute/path/file] [--insecure]
```

Base URL:

```bash
https://api.pokoclan.com
```

読み取り例:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py GET https://api.pokoclan.com/health --token "$TOKEN"
```

投稿例:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py POST https://api.pokoclan.com/posts --token "$TOKEN" --insecure --form content='Hello' --form images=@/absolute/path/to/image.png
```

## ルール

- `content` はインライン文字列。
- `images` はローカルファイル。
- リモート画像は先にダウンロード。
- `--insecure` は TLS 失敗時のみ。

## 分担

- `pokoclan-post` は調査と下書き。
- `pokoclan-api` はアップロードと発行。
