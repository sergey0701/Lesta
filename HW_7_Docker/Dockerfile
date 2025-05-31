# Stage 1: Build
FROM golang:1.21 AS builder

WORKDIR /app

COPY main.go .

RUN go build -o /bin/web ./main.go

# Stage 2: Run
FROM alpine:latest

COPY --from=builder /bin/web /bin/web

EXPOSE 8080

CMD ["/bin/web"]
