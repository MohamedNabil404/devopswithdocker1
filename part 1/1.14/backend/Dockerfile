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
RUN go build -o server



# Expose the default port (can be overridden via environment variable)
EXPOSE 8080

# Set default environment variables
ENV PORT=8080
ENV REQUEST_ORIGIN="http://localhost:5000"

# Run the binary
CMD ["./server"]