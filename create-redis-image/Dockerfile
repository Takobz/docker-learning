# Get base image
FROM alpine

# run command to install redis
RUN apk add --update gcc
RUN apk add --update redis

# startup command
CMD ["redis-server"]