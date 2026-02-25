# Use official Node image
FROM node:18-alpine

# Create app directory
WORKDIR /app

# Copy package files first (for better caching)
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy remaining application files
COPY . .

# Expose application port (change if your app uses different port)
EXPOSE 5000

# Start the app
CMD ["node", "server.js"]
