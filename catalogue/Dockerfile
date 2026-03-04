#multi stage builds 243mb
FROM node:20-alpine3.23 AS builder 
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20-alpine3.23
RUN addgroup -S roboshop-project && adduser -S roboshop -G roboshop-project
WORKDIR /opt/server
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
USER roboshop
COPY --from=builder /opt/server /opt/server
CMD ["node", "server.js"]


# #optimizing the image takes memory only 600mb 
# FROM node:20-alpine3.23
# # Create a group and user
# RUN addgroup -S roboshop-project && adduser -S roboshop -G roboshop-project
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# RUN chown -R roboshop:roboshop-project /opt/server
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# USER roboshop
# CMD ["node", "server.js"]

#normal docker image takes memory is high like 1.25gb 
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
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# # Default command to start the Node.js application
# CMD ["node", "server.js"]
