# Pull in base (parent) image
FROM node:17-alpine

# Install nodemon - auto restart server upon changes detected
RUN npm install -g nodemon

# Define working dir
WORKDIR /app

# Copy dependency list to we can install those right away or skip if nothing changes
COPY package*.json .

# Load npm dependencies (command execute in /app dir)
RUN npm install

# Copy source files <path_where_dockerflie_lives> into docker working path => host './api/*'  copied to 'container./app'
COPY . .

# Specify which port this container should listen on (if any)
# Note: required for docker desktop port mapping 
EXPOSE 4000
# required for docker desktop port mapping

CMD ["npm", "run", "dev"]


----------------------------------

## Note that in the package.json where we define the "dev" script, we use the '-L' flag. This is needed for Docker to work with nodemon when runnin on a Windows machine. 
# Build [docker file]: -> cd api && sudo docker build -t mynodeapi_img:1.0 .

### Run container on port 4000

# - Option 1 (no volume)
    # sudo docker run --name mynodeapp_c1-p 4000:4000 --rm mynodeapi_img:1.0
    # Adding "rm" above to remove container once stopping.


# - Option 2 (with volume)
    # Format:
        # sudo docker run --name mynodeapp_c1-p 4000:4000 --rm -v <local_dir>:<container_dir> -v /app/node_modules mynodeapi_img:1.0

    # Example:
        # sudo docker run --name mynodeapp_c1-p 4000:4000 --rm -v C:\Users\Me\Documents\mydockerapp\:/dockerapp -v /app/node_modules mynodeapi_img:1.0