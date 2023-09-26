# Pull in base (parent) image
FROM node:17-alpine

# Define working dir
WORKDIR /app

# Copy dependency list to we can install those right away or skip if nothing changes
COPY package*.json .

# Load npm dependencies (command execute in /app dir) 
RUN npm install
# *! The RUN command is executed within the Docker container whereas EXEC is executed in host system

# Copy source files <path_where_dockerflie_lives> into docker working path => host './api/*'  copied to 'container./app'
COPY . .

# Specify which port this container should listen on (if any)
# Note: required for docker desktop port mapping 
EXPOSE 4000

CMD ["node", "app.js"]

# Build docker file: -> cd api && sudo docker build -t mynodeapi_img:1.0 .
# Run container on port 4000 => sudo docker run --name mynodeapp_c1 -d -p 4000:4000 mynodeapi_img:1.0
