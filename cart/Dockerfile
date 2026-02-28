#nodejs installing from the dockerhub
FROM node:20
# creating the work directory 
WORKDIR /opt/server
# copying the json file application file
COPY *.js .
# copying the js file application file
COPY package.json .
# downloading  the dependencies 
RUN npm install
#setuping the environments connection b/w user and redis and mongodb
ENV REDIS_HOST=redis \
    CATALOGUE_HOST=catalogue \
    CATALOGUE_PORT=8080
# Default command to start the Node.js application
CMD ["node", "server.js"]