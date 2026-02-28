#nodejs installing from the dockerhub
FROM node:20
# creating the work directory 
WORKDIR /opt/server
# copying the json file application file
COPY package.json .
# copying the js file application file
COPY *.js .
# downloading  the dependencies 
RUN npm install
#setuping the environments connection b/w user and redis and mongodb
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
# Default command to start the Node.js application
CMD ["node", "server.js"]
