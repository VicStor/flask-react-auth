# pull official base image
FROM node:12.7.0-alpine

# set working directory
WORKDIR /usr/src/app

# add `/usr/src/app/node_modules/.bin` to $PATH
ENV PATH /usr/src/app/node_modules/.bin:$PATH

# install and cache app dependencies
COPY package.json /usr/src/app/package.json
COPY package-lock.json /usr/src/app/package-lock.json

RUN npm install -g pm2
RUN npm ci
RUN npm ls -g --depth=0

# start app
CMD ["npm", "start"]
