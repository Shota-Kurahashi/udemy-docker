# section 6

## Dockerfile によるイメージの作成

```dockerfile
FROM ubuntu:latest -> ベースイメージの指定
```

## Dockerfile のビルド path は Dockerfile のあるディレクトリでないといけないわけではない。指定したディレクトリ以下のファイルすべてを Docker demon に送る

```bash
docker image build -t <イメージ名>:<タグ> <Dockerfileのパス>　

or

docker  build -t <イメージ名>:<タグ> <Dockerfileのパス>
```

## RUN -> コマンドを実行する

```dockerfile
RUN apt-get update && apt-get install -y curl
```

## ファイルをコピーする (コピー先がなくても自動で作成される)

```dockerfile
COPY <コピー元> <コピー先>
```

## docker ファイルの場所を指定する

```bash
docker image build -t <イメージ名>:<タグ> -f <Dockerfileのパス>　<build contextパス>
```

## CMD -> コンテナ実行時のデフォルトコマンドを指定する

```dockerfile
CMD ["echo", "hello world"]
```
