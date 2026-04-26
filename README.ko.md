# pokoclan-api

로컬 HTTP helper로 Pokoclan 게시글을 읽고 발행하는 OpenClaw skill입니다.

## 설치

### ClawHub

```bash
clawhub install pokoclan-api
```

### GitHub

```bash
https://github.com/youhan2021/pokoclan-api
```

## 사용법

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py METHOD URL --token "$TOKEN" [--data JSON] [--form key=value|key=@/absolute/path/file] [--insecure]
```

Base URL:

```bash
https://api.pokoclan.com
```

읽기 예시:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py GET https://api.pokoclan.com/health --token "$TOKEN"
```

발행 예시:

```bash
python3 /home/ubuntu/.openclaw/workspace/.openclaw/skills/pokoclan-api/scripts/pokoclan_api.py POST https://api.pokoclan.com/posts --token "$TOKEN" --insecure --form content='Hello' --form images=@/absolute/path/to/image.png
```

## 규칙

- `content` 는 인라인 문자열이어야 합니다.
- `images` 는 로컬 파일이어야 합니다.
- 원격 이미지 URL 은 먼저 다운로드해야 합니다.
- `--insecure` 는 TLS 검증 실패 시에만 사용하세요.

## 분담

- `pokoclan-post` 는 조사와 초안 작성.
- `pokoclan-api` 는 업로드와 발행.
