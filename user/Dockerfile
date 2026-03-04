FROM node:20-alpine3.23 AS builder
WORKDIR /opt/server
COPY *.js .
COPY package.json .
RUN npm install

FROM node:20-alpine3.23
RUN addgroup -S roboshop-project && adduser -S roboshop -G roboshop-project
WORKDIR /opt/server
ENV MONGO="true" \
    REDIS_URL='redis://redis:6379' \
    MONGO_URL="mongodb://mongodb:27017/users"
COPY --from=builder /opt/server /opt/server
USER roboshop
CMD ["node", "server.js"]


# #nodejs installing from the dockerhub
# FROM node:20
# # creating the work directory 
# WORKDIR /opt/server
# # copying the json file application file
# COPY package.json .
# # copying the js file application file
# COPY *.js .
# # downloading  the dependencies 
# RUN npm install
# #setuping the environments connection b/w user and redis and mongodb
# ENV MONGO="true" \
#     REDIS_URL='redis://redis:6379' \
#     MONGO_URL="mongodb://mongodb:27017/users"
# # Default command to start the Node.js application
# CMD ["node", "server.js"]