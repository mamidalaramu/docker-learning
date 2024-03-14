# Use the official Node.js image from Docker Hub
FROM node

# Set the working directory inside the container
WORKDIR /app

# Copy package.json file from the host to the working directory in the container
COPY package.json /app

# Install dependencies defined in package.json
RUN npm install

# Copy the rest of the application files from the host to the working directory in the container
COPY . /app

# Expose port 80 to allow communication to the Node.js application
EXPOSE 80

# Define the command to run the Node.js server when the container starts
CMD ["node", "server.js"]
