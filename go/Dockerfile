FROM golang:alpine as builder

WORKDIR /app

COPY app.go .

RUN GOOS=linux go build ./app.go

### Define the running image
FROM scratch
WORKDIR /app
COPY --from=builder /app/app .
CMD ["/app/app"]