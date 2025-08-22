FROM golang:latest

WORKDIR /

COPY . .

RUN go build -o excalibur src/main.go

CMD [ "./excalibur" ]
