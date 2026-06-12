# all of that are the insturctions for an image

# allows us to build our image which will be built up on another image
#   it must exist on your system or under that name on docker hub
FROM node
# tells docker that all the subsequent commands will be executed inside this folder
WORKDIR /app

COPY package.json /app
# this will be executed when the image is created
RUN npm install
# which files should go into our image
#  first dot means that it should take files that are on the same level as dockerfile
#  /app is the path inside of the image where those files should be stored
#  e.g. images have their own file system
COPY . /app
# tells which port an app is listening to. 
#   (this is more like for docs. it is not actually exposing)
#       so it is optional, but yet recomended
EXPOSE 80
# this will run when a container is started based on an image
# if yo do not specify an CMD, it will have the base built in one, if you do not have it to, it will be an error
CMD ["node", "server.js"]