# Use the official Node.js image as the base image
FROM node:18 as build

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code, excluding node_modules
COPY . .

# Build the Svelte app using Vite
RUN npm run build

# Expose the port the app runs on
EXPOSE 3000

# Define the command to run the app using Vite
CMD ["npm", "run", "preview"]
