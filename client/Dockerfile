# Use a lighter version of Node as a parent image
FROM node:10-alpine

# Create working directory for the application code
WORKDIR /usr/src/client

# copy package.json into the container
COPY package*.json ./

# install dependencies
RUN npm install

# Copy the current directory contents to the working directory
COPY . .

#Create a build directory with a production build of the app
RUN npm run build

#Install serve
RUN npm install -g serve

# Make port 3000 available to the world outside this container
EXPOSE 3000

# Run the app when the container launches
CMD ["serve", "-s", "build", "-l", "3000" ]