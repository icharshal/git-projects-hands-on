# node-web-server

FROM node:4.6
WORKDIR /app
ADD . /app
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]


docker run -it -d -p 3000:3000 node-web-server    


docker-machine ip # it will give you ip of docker 

at your teminal local_ip:3000
