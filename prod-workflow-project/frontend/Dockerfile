# This assumes the docker file will be called from the root of the project
#phase called builder - Build Phase
FROM node:16-alpine as builder

# specify the working directory that will be used in my container
WORKDIR '/app'
# copy all the dependencies needed
COPY ./prod-workflow-project/frontend/package.json .
# install dependencies
RUN npm install
# copy the source in currenct directory
COPY ./prod-workflow-project/frontend .
# build our app for product
RUN npm run build

# run phase
FROM nginx
# For ElasticBeanStalk to map port to incoming trafic.
EXPOSE 80
# copy build folder --from=<phase-name>
# copies app/build contents from builder phase to specified dir. /usr/share/nginx/html is nginx default dir for hosting static sites
# ngnix base image has startup command to start nginx server.
COPY --from=builder /app/build /usr/share/nginx/html

