---
title: "Docker Desktop 메모리 사용량 줄이기"
description: "wmmem 메모리 사용량 문제 해결"
pubDate: 'Jun 01 2026'
---

# 문제

Docker Desktop 실행 후 wmmem 메모리가 과도하게 증가했다.

# 원인

WSL2가 캐시 메모리를 계속 보유하고 있었다.

# 해결

`.wslconfig` 파일 생성

```ini
[wsl2]
memory=8GB
processors=4
```

WSL 재시작

```bash
wsl --shutdown
```

# 결과

메모리 사용량이 정상 수준으로 감소했다.

# 참고

- Docker Desktop
- WSL2