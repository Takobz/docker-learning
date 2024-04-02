# Base image with npm installed
# alpine is a lightweight linux distribution
FROM node:14-alpine

# Specifies the working directory
# Every command under this line will be executed in /usr/app
WORKDIR /usr/app

# copy all files from the current directory to the container
# if we had the following:
# COPY ./ ./
# RUN npm install
# Then changing any file copied from current directory will cause npm install to run again even if we don't want that to happen.

#To resolve the above issue we do the following.
# This way if any file changes that is not the package.json npm install won't re-run.
# Order matters and always copy smartly :)
COPY ./package.json ./
RUN npm install
COPY ./ ./

#Default command
CMD [ "npm", "start" ]