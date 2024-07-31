FROM golang:alpine AS builder

WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download

COPY . .
RUN go build -o mysql-adapter .

FROM alpine
WORKDIR /app

COPY --from=builder /app/mysql-adapter /usr/local/bin/mysql-adapter
EXPOSE 8080
CMD ["mysql-adapter"]
