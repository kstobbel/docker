FROM node:alpine
MAINTAINER Kevin Stobbelaar <kstobbelaar@gmail.com>

# Install git
RUN apk update
RUN apk add git

# Clone microservice implementation from github
RUN git clone https://github.com/kstobbel/microservice-hello-node.git

# Go in to microservice directory and install dependencies
WORKDIR /microservice-hello-node
RUN npm install

EXPOSE 3000
CMD [ "npm", "node index.js" ]
