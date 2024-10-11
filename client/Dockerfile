# Dockerfile for Nuxt.js Client

# Use a compatible Node.js version
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json files
COPY package*.json ./

# Install dependencies with legacy peer deps flag
RUN npm install --legacy-peer-deps

# Copy the rest of the application
COPY . .

# Expose the port that the Nuxt.js app runs on
EXPOSE 3000

# Start the application
CMD ["npm", "run", "dev"]
