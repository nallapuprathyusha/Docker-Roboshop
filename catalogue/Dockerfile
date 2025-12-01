#Uses official Node.js v20 image from Docker Hub.
FROM node:20

#This creates and switches into /opt/server.
#All following commands run inside this folder.
WORKDIR /opt/server

#Copies package.json and all .js files from your local directory into the container.
#COPY source dest
COPY package.json .
COPY *.js .

#Executes npm install inside the container,
#installing dependencies into /opt/server/node_modules.
RUN npm install

#ENV key=value 
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"=value


#When the container starts → run node server.js.
CMD ["node","server.js"]

