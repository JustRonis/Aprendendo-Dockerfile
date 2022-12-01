FROM golang

WORKDIR /app

ADD . /app

RUN go build tokeira.go

ENTRYPOINT ./tokeira

