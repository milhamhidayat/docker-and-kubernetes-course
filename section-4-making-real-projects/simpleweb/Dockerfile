# Specify a base image
FROM node:alpine

WORKDIR /usr/app

# Install some dependencies
COPY ./package.json ./
COPY ./package-lock.json ./
RUN npm install
COPY ./ ./

# Default command
CMD ["npm","start"]