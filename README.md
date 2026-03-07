# ALICE-Edge-AI

Edge device AI inference pipeline — deploy ternary models to IoT devices

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-ml, alice-edge, alice-rtos, alice-bridge, alice-cache

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/deploy` | エッジデバイスへモデルデプロイ |
| `POST` | `/api/v1/infer` | エッジ推論実行 |
| `GET ` | `/api/v1/devices` | 接続デバイス一覧 |
| `GET ` | `/api/v1/metrics` | 推論メトリクス |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
