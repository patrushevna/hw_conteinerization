FROM golang:alpine as builder

ENV CGO_ENABLED 0
ENV GOOS linux

WORKDIR /build
COPY golang/ .
RUN go build -o hello .


FROM alpine

WORKDIR /build
COPY --from=builder /build/hello /build/hello
CMD ["./hello"]
