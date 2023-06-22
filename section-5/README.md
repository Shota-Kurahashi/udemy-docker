# docker section-5

container run のオプションを使ってみる。

### -i -> 標準入力が使えるようになる

```bash
docker container run -i ubuntu:latest
```

### -t -> 見た目を整形した形で表示をする

```bash
docker container run -t ubuntu:latest
```

### -it -> -i と -t を同時に使う

```bash
docker container run -it ubuntu:latest
```

### inspect -> コンテナの詳細情報を取得する

```bash
docker container inspect <コンテナID>

or

docker image inspect <イメージID or イメージ名>
```

### exec -> コンテナ内でコマンドを実行する

```bash
docker container exec <コンテナID> <コマンド>
```

### exec と run の違い

exec は既存のコンテナを使ってコマンドを実行する。run は image から新しいコンテナを作成してコマンドを実行する。

### --name -> コンテナに名前をつける

```bash
docker container run --name <コンテナ名> <イメージ名>
```

### prune -> Up していないコンテナを削除する

```bash
docker container prune
```

### --rm -> コンテナを終了したら自動で削除する

```bash
docker container run --rm <イメージ名>
```

### --rm -f -> コンテナを強制終了したら自動で削除する

```bash
docker container run --rm -f <イメージ名>
```

### フォアグラウンドとデタッチドモード (通常はフォアグラウンドで実行される) -d -> デタッチドモードで実行する

```bash
docker container run -itd <イメージ名>
```
