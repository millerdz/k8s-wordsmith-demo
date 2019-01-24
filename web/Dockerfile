# BUILD
FROM golang:1.11.5-alpine3.8 as builder

COPY dispatcher.go .
RUN go build dispatcher.go

# RUN
FROM alpine:edge

EXPOSE 80
CMD ["/dispatcher"]

COPY --from=builder /go/dispatcher /
COPY static /static/
