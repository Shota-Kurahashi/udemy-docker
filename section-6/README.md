# section 6

### Dockerfile によるイメージの作成

```dockerfile
FROM ubuntu:latest -> ベースイメージの指定
```

### Dockerfile のビルド path は Dockerfile のあるディレクトリでないといけないわけではない。指定したディレクトリ以下のファイルすべてを Docker demon に送る

```bash
docker image build -t <イメージ名>:<タグ> <Dockerfileのパス>　

or

docker  build -t <イメージ名>:<タグ> <Dockerfileのパス>
```

### RUN -> コマンドを実行する

```dockerfile
RUN apt-get update && apt-get install -y curl
```

### ファイルをコピーする (コピー先がなくても自動で作成される)

```dockerfile
COPY <コピー元> <コピー先>
```

### docker ファイルの場所を指定する

```bash
docker image build -t <イメージ名>:<タグ> -f <Dockerfileのパス>　<build contextパス>
```

### CMD -> コンテナ実行時のデフォルトコマンドを指定する

```dockerfile
CMD ["echo", "hello world"]
```

### docker layer の確認方法

```bash
docker image history <イメージ名>:<タグ>
```

###　環境変数の設定

```dockerfile
ENV <環境変数名>=<値>
```

### ARG -> docker build 時に指定する変数

```dockerfile
ARG <変数名>

or

ARG <変数名>=<デフォルト値>
```

### 変数を渡しながら docker build

```bash
docker image build --build-arg <変数名>=<値> -t <イメージ名>:<タグ> <Dockerfileのパス>
```

### ARG と ENV の違い

- ARG は docker build 時に指定する変数
- ARG は イメージ作成時のみの一時的の変数
