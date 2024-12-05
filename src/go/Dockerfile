FROM golang:1.23.4-alpine as builder

WORKDIR /usr/src/app

COPY . .

RUN go build -ldflags="-s -w" main.go

FROM scratch
COPY --from=builder /usr/src/app/ .
CMD ["./main"]