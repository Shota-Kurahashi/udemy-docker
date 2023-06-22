# docker section-7

### 他の image から COPY する

```Dockerfile
# コンパイル
FROM gcc:12.2.0

WORKDIR /app

COPY ./hello.c .

RUN gcc hello.c

# 実行

FROM ubuntu:20.04

WORKDIR /app

# 0番目の image からコピーする

COPY --from=0 /app/a.out .
```

### index ではなく、image 名で指定する

```Dockerfile
# コンパイル
FROM gcc:12.2.0 AS compiler


WORKDIR /app

COPY ./hello.c .

RUN gcc hello.c

# 実行

FROM ubuntu:20.04

WORKDIR /app

COPY --from=compiler /app/a.out .
```
