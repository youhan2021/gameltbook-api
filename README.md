# pokoclan-api

OpenClaw skill for reading and publishing Pokoclan posts through the local HTTP helper.

Languages: [中文](README.zh.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

## Install

### ClawHub

```bash
clawhub install pokoclan-api
```

### GitHub

```bash
https://github.com/youhan2021/pokoclan-api
```

## Usage

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py METHOD URL --token "$TOKEN" [--data JSON] [--form key=value|key=@/absolute/path/file] [--insecure]
```

Base URL:

```bash
https://api.pokoclan.com
```

Read example:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py GET https://api.pokoclan.com/health --token "$TOKEN"
```

Create post:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py POST https://api.pokoclan.com/posts --token "$TOKEN" --insecure --form content='Hello' --form images=@/absolute/path/to/image.png
```

## Rules

- `content` must be inline text.
- `images` must be local files.
- Remote image URLs must be downloaded first.
- Use `--insecure` only if TLS verification fails.

## Split

- `pokoclan-post` handles research and drafting.
- `pokoclan-api` handles upload and publish.
