# Use the official Node.js 20 image as the base image
FROM node:20

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install the dependencies
RUN npm install

# Install react-scripts globally
RUN npm install -g react-scripts

# Copy the rest of the application's source code to the container
COPY . .

# Fix permission issues on node_modules binaries
RUN chmod +x ./node_modules/.bin/*

# Build the React.js application
RUN npm run build

# Expose the port that the application listens on
EXPOSE 3001

# Start a simple web server to serve the built React.js files
CMD [ "npx", "serve", "-s", "build" ]
