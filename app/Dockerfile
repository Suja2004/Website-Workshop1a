# Base image 
FROM node:18-alpine

# Install build dependencies
RUN apk add --no-cache libc6-compat build-base

# Create a directory to hold the application code inside the image
WORKDIR /app

# Copy package.json and yarn.lock first to leverage Docker caching
COPY package.json yarn.lock ./

# Install app dependencies
RUN yarn install --production

# Copy the rest of the application code
COPY . .

# Expose the application port
EXPOSE 3000

# Start the application
CMD ["node", "/app/src/index.js"]
