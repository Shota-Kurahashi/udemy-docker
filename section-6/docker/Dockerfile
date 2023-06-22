FROM ubuntu:20.04

ENV hello="Hello World"

ARG message_arg="Message Arg"
ENV env="Message Env"

RUN echo $message_arg > message_arg.txt
RUN echo $env > message_env.txt

CMD ["bash"]


