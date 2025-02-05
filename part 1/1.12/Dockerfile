# Single-stage image
FROM node:16-alpine

WORKDIR /app

# 1. Copy package files first for layer caching
COPY package*.json ./

# 2. Install dependencies (including devDependencies needed for build)
RUN npm install

# 3. Copy ALL source files (missing in your original version)
COPY . .

# 4. Build the app (now has access to source files)
RUN npm run build

# 5. Install serve globally (as root)
RUN npm install -g serve

# 6. Create non-root user for security
RUN adduser -D appuser

# 7. Switch to non-root user
USER appuser

# 8. Expose port and start the server
EXPOSE 5000
CMD ["serve", "-s", "-l", "5000", "build"]