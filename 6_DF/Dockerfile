FROM golang AS buildando

WORKDIR /app

ADD . /app

RUN go build tokeira.go

FROM alpine
#multistage

WORKDIR /giropops
COPY --from=buildando /app/tokeira /giropops/

ENTRYPOINT ./tokeira

