FROM golang:1.17 AS builder


WORKDIR /app


RUN git clone --depth 1 -b master https://github.com/amirbokaei/gohttpserver.git .


RUN CGO_ENABLED=0 GOOS=linux go build -o myapp


FROM alpine:latest


WORKDIR /app


COPY --from=builder /app/myapp .


WORKDIR /wp-content/uploads


EXPOSE 8000


CMD ["/app/myapp"]
