# Base image with npm installed
# alpine is a lightweight linux distribution
FROM node:14-alpine

# copy all files from the current directory to the container
COPY ./ ./

RUN npm install

CMD [ "npm", "start" ]