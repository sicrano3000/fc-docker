FROM golang:alpine3.14 as builder

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 go build -o /main main.go

FROM scratch

WORKDIR /

COPY --from=builder /main /main

EXPOSE 8080

ENTRYPOINT ["/main"]