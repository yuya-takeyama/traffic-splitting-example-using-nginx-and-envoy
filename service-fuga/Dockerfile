FROM golang:1.13.6-alpine3.11 as builder

WORKDIR /app
ADD . /app
RUN CGO_ENABLED=0 GOOS=linux go build -a -ldflags '-extldflags "-static"'

FROM busybox
COPY --from=builder /app/service-fuga /app/service-fuga
CMD ["/app/service-fuga"]
