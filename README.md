# go-gin-example

Ginのサンプルリポジトリ。

## Usage

### Develop

ホットリロード対応の開発環境が以下で立ち上がる。

```bash
docker compose up
```

### Production

Dockerfileはマルチステージングビルドで構成されているため、単体のコンテナとして任意のクラウドサービスにそのままデプロイを行い利用することを想定。
