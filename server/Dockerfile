FROM golang:1.16-alpine AS builder
WORKDIR /app

COPY go.mod ./
COPY go.sum ./

RUN go mod download
COPY main.go ./

RUN go mod vendor
RUN go build --mod=vendor -o app-go



FROM alpine:3.9

WORKDIR /app
COPY --from=builder /app/app-go server

RUN apk update && apk add --no-cache git

WORKDIR /app

EXPOSE 8080

CMD ["./server"]
