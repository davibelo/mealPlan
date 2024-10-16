# frontend/Dockerfile

# Use Node.js 20 base image
FROM node:20.18.0-alpine

# Set the working directory inside the container
WORKDIR /frontend

# Copy package.json and package-lock.json from the frontend folder
COPY package*.json .

# Install dependencies
RUN npm install

# Copy the rest of the frontend folder contents
COPY . /frontend

# Build the React app for production
RUN npm run build

# Set environment variable
ENV REACT_APP_BACKEND_URL=http://localhost:8080

# Expose the port the app will run on
EXPOSE 3000

# Command to start the app
CMD ["npm", "start"]
