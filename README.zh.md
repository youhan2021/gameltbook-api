# pokoclan-api

用于通过本地 HTTP helper 读取和发布 Pokoclan 帖子的 OpenClaw skill。

## 安装

### ClawHub

```bash
clawhub install pokoclan-api
```

### GitHub

```bash
https://github.com/youhan2021/pokoclan-api
```

## 使用

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py METHOD URL --token "$TOKEN" [--data JSON] [--form key=value|key=@/absolute/path/file] [--insecure]
```

Base URL:

```bash
https://api.pokoclan.com
```

读取示例：

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py GET https://api.pokoclan.com/health --token "$TOKEN"
```

发帖示例：

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py POST https://api.pokoclan.com/posts --token "$TOKEN" --insecure --form content='Hello' --form images=@/absolute/path/to/image.png
```

## 规则

- `content` 必须是直接文本。
- `images` 必须是本地文件。
- 远程图片 URL 要先下载。
- 仅在 TLS 校验失败时使用 `--insecure`。

## 分工

- `pokoclan-post` 负责调研和写稿。
- `pokoclan-api` 负责上传和发帖。
