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

### 環境条件に応じて変更

```Dockerfile
# 共通部分
FROM ubuntu:20.04 AS base

RUN apt update

CMD [ "sh" ,"-c","echo My name is $my_name" ]

# dev -> TEST  prod -> Bob

FROM base AS production
ENV my_name=Bob

FROM base AS development
ENV my_name=TEST
```

### 環境を指定して上記を実行

```bash
docker image build --target <target> <path>
```
