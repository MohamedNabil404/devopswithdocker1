# Use the official Go 1.16 Alpine image
FROM golang:1.16-alpine

# Set working directory
WORKDIR /app

# Copy go.mod and go.sum first for dependency caching
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the entire project
COPY . .

# Build the project
RUN go build

# Expose the default port
EXPOSE 8080


# Run the binary
CMD ["./server"]