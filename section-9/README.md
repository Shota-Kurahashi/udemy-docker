# docker section-9

### ホストとコンテナのファイル共有コンテナを紐付ける

```bash
docker container run -p <ホスト側のポート>:<コンテナ側のポート> <イメージ>
```

### ネットワークの一覧を表示する

```bash
docker network ls
```

### ネットワークの詳細を表示する

```bash
docker network inspect <ネットワーク名>
```

### ネットワークを作成する

```bash
docker network create <ネットワーク名>
```

### 作成したネットワークにコンテナを紐付ける

```bash
docker container run -itd --name <コンテナ名> --network <ネットワーク名> <イメージ>
```

名前指定の curl などを使う場合は自作のネットワークを作成する必要がある
