# Use Ubuntu 22.04 as the base image
FROM ubuntu:22.04

# Set the working directory
WORKDIR /app

# Install curl
RUN apt-get update && \
    apt-get install -y curl && \
    rm -rf /var/lib/apt/lists/*

# Copy the script into the container
COPY hello.sh .

# Make it executable
RUN chmod +x hello.sh

# Define the default command to run the script
CMD ["./hello.sh"]