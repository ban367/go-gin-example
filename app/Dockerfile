FROM golang:1.19.4 as builder

WORKDIR /app
COPY . .

RUN go mod download
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main ./main.go

# 以下は開発環境用
RUN go install github.com/cosmtrek/air@latest
CMD ["air", "-c", ".air.toml"]

FROM alpine:latest as production

WORKDIR /app
COPY --from=builder /app/main ./

CMD ["./main"]
