# syntax=docker/dockerfile:1

FROM golang:1.16-alpine

RUN mkdir /app

ADD . /app

WORKDIR /app

COPY go.mod ./
COPY go.sum ./
RUN go mod download

COPY *.go ./

RUN go build -o /docker-auth-api

EXPOSE 3008

CMD [ "/docker-auth-api" ]