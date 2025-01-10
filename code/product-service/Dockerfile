# Build stage
FROM golang:1.23-alpine AS build
WORKDIR /app
COPY . .
RUN go build -o main .

# Runtime stage
FROM alpine:3.20
WORKDIR /app
COPY --from=build /app/main .
EXPOSE 8989
CMD ["./main"]