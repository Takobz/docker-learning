#phase called builder - Build Phase
FROM node:16-alpine as builder

# specify the working directory that will be used in my container
WORKDIR '/app'
# copy all the dependencies needed
COPY package.json .
# install dependencies
RUN npm install
# copy the source in currenct directory
COPY . .
# build our app for product
RUN npm run build

# run phase
FROM nginx
# copy build folder --from=<phase-name>
# copies app/build contents from builder phase to specified dir. /usr/share/nginx/html is nginx default dir for hosting static sites
# ngnix base image has startup command to start nginx server.
COPY --from=builder /app/build /usr/share/nginx/html

