# Use the official Golang image as the base image for building the app
FROM golang:1.24-alpine AS builder

# Set the Current Working Directory inside the container
WORKDIR /app

# Copy the go.mod file to download dependencies
COPY go.mod ./
RUN go mod download

# Copy the entire source code into the container
COPY . .

# Build the Go application and create an executable named 'go-app'
RUN go build -o go-app

# Use a lightweight Alpine Linux image for running the built application
FROM alpine:latest

# Set the working directory inside the runtime container
WORKDIR /root/

# Copy the compiled binary from the builder stage to the runtime container
COPY --from=builder /app/go-app .

# Expose port 8080 for incoming traffic
EXPOSE 8080

# Command to run the compiled Go application
CMD ["./go-app"]
