FROM ubuntu:20.04

ENV hello="Hello World"

ARG message

RUN echo $message > message.txt

CMD ["cat", "message.txt"]


