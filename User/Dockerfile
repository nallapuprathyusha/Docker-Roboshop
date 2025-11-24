#Use Node.js version 20 as the base image.
#Includes Node runtime and npm.
FROM node:20

#This creates and switches into /opt/server.
#All following commands run inside this folder.
WORKDIR /opt/server

#Declares that the container listens on port 8080.
#Useful for documentation and linking containers.
EXPOSE 8080


#Copies package.json and all .js files from your local directory or HOST into the container.
#syntax - COPY source dest
#install dependencies first.
COPY package.json .
#application code
COPY *.js . 


#Executes npm install inside the container,
#installing dependencies into /opt/server/node_modules.
RUN npm install

#ENV MONGO, REDIS_URL, MONGO_URL
#Sets environment variables inside the container.
#Node.js app can read these to connect to MongoDB and Redis.
#syntax - ENV key=value 
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"=value


#When the container starts → run node server.js.
CMD ["node","server.js"]

