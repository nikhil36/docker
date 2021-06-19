# Objective:  Launch node.js app to track ToDo tasks

# Defining a Parent image here
FROM node:10-alpine

# Create node app folder in the container and set the appropriate owner
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

# Set the working directory
WORKDIR /home/node/app

# Add package files to container:
# We can use COPY or ADD
# COPY - copy file from base container
# ADD  - add file from a remote source like github etc.
COPY package*.json ./

# Set npm registry
RUN npm config set registry http://registry.npmjs.org/

# Install npm pre reqs
RUN npm install

# Copy all files from the npm folder and set the owner
COPY --chown=node:node . .

# Set user to run all commands going forward
USER node

# Expose 8080 port for access
EXPOSE 8080

# Define command we wanna run on launch
# Preferred way is to provide an array with first element as the command and then args
CMD ["node","index.js"]


# Now we just need to run the build command from the directory, -t for the image name
#   docker build . -t appimage
#  
# We can now run our container.
#   docker run -dt --name app01 appimage
#
# Get the IP address
# docker inspect app01 | grep IPAddress
# curl <Address>:8080



