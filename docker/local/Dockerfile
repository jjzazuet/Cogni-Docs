# Use official Bun image
FROM docker.io/oven/bun:latest

# Set working directory
WORKDIR /app

# Copy package files for dependency installation
COPY package.json ./

# Install dependencies
RUN bun install

# Copy application code
COPY app/ ./app/
COPY tsconfig.json ./

# Expose the HTTP port
EXPOSE 3001

# Set default command to run the MCP server
CMD ["bun", "run", "app/index.ts"]

