#If the image node has been installed previously on the docker, then it will not download again from Docker Hub, it will take the local copy, otherwise it will download from Docker Hub.
#You can also specify local images that you have created in the FROM, just make sure to add all images you need to the FROM instruction here. 
FROM node

WORKDIR /app

COPY package.json /app

#The below command will install all dependencies mantioned in the package.json file
RUN npm install

# it will copy all files from the current directory into the relative path ./ of the container which root is /app specified in the WORKDIR instruction above.
# If workdir is not specified, then you have to provide the full plath within the container like this "COPY . /app"
COPY . /app

#Remember that containers do not expose any ports outside of the container, to expose a certain port you have to use the EXPOSE instruction:
EXPOSE 80
#Look at the server.js file it is listening at port 80  "app.listen(80);" hence you have to expose that port when setting up the container. HOWEVER: THIS INSTRUCTION HERE IS ONLY TO DOCUMENT IT, AND IT DOES NOT DO ANYTHING TO REALLY EXPOSE THE PORT.

#In order to correctly expose the port that the app is listening ("80") you have to run the container as follows:

#docker run -p 3000:80 <id of the image>   
# then the container will expose the internal port 80 into the port 3000, then you can access in the web browser as:
#localhost:3000 
#And the app will show up

#This will run node inside the container once the image is ran. The difference with the Run command is that CMD executes once the container is created, while the run command is executed when before the container is created.
CMD ["node", "server.js"]

