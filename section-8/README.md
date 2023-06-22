# docker section-8

volume -> docker が管理している外付け HDD みたいなようなもの。コンテナが消えてもデータは残る。

### volume の作成

```bash
docker volume create <volume-name>
```

### volume の確認

```bash
docker volume ls
```

### volume の詳細確認

```bash
docker volume inspect <volume-name>
```

### volume の削除

```bash
docker volume rm <volume-name>
```

### volume に接続しながらコンテナを起動 -v と --mount は同じ

```bash
docker container run -v <vol名>:<コンテナ内の絶対パス> <image>

# or

docker container run --mount type=volume src=<vol名>,dst=<コンテナ内の絶対パス> <image>
```

## バインドマウントしながらコンテナを起動

```bash
docker container run -v <ホストの絶対パス>:<コンテナ内の絶対パス> <image>

# or

docker container run --mount type=bind,src=<ホストの絶対パス>,dst=<コンテナ内の絶対パス> <image>
```

### バインドマウントと volume の違い

- バインドマウントはホストからアクセス可能
- volume はホストからアクセス不可
