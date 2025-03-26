FROM node:18 AS build


WORKDIR /app


#install dependencies
COPY package.json ./
RUN npm install

#Copy the rest of the application code
COPY . .


#build the application
RUN npm run build

#use the offical nginx image

FROM  nginx:alpine

#set the working directory in the container

COPY  --from=build /app/build /usr/share/nginx/html

#Expose the frontend port
EXPOSE 80

