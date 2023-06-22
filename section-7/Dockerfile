# コンパイル
FROM gcc:12.2.0 AS compiler

WORKDIR /app

COPY ./hello.c .

RUN gcc hello.c

# 実行

FROM ubuntu:20.04

WORKDIR /app

COPY --from=compiler /app/a.out .

CMD ["./a.out"]