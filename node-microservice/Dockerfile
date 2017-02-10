FROM node:alpine
MAINTAINER Kevin Stobbelaar <kstobbelaar@gmail.com>

# Install git
RUN apk update
RUN apk add git

# Clone microservice implementation from github
RUN git clone https://github.com/kstobbel/microservice-hello-node.git

EXPOSE 8080
CMD [ "npm", "start" ]
