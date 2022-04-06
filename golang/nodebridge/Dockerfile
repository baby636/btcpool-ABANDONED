FROM golang:1.13-alpine as builder

RUN apk add --no-cache gcc git linux-headers musl-dev

ADD . /btcpool
RUN cd /btcpool && go get ./...

FROM alpine:3.15.4

RUN apk add --no-cache ca-certificates
COPY --from=builder /go/bin/* /usr/local/bin/
