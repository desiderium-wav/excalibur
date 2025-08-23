FROM golang:1.22 AS builder

WORKDIR /app

COPY src/go.mod src/go.sum ./

RUN go mod download

COPY src/ .

RUN go build -o excalibur .

FROM gcr.io/distroless/base-debian12

WORKDIR /app

COPY --from=builder /app/excalibur .

CMD [ "/app/excalibur" ]
