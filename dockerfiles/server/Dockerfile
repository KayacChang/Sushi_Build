# Build
FROM golang:alpine as builder

WORKDIR /bin
COPY ./server .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o run

# Main

FROM scratch

WORKDIR /root/

COPY --from=builder /bin .

ENTRYPOINT ["./run"]