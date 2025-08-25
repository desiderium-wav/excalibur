FROM golang:1.22-alpine AS builder
WORKDIR /app

COPY go.mod go.sum ./
RUN go mod download

COPY . .

RUN go build -o excalibur .

FROM alpine:latest
WORKDIR /app

COPY --from=builder /app/excalibur .

EXPOSE 8080

CMD ["./excalibur"]
