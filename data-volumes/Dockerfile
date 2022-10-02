FROM node:14

ARG DEFAULT_PORT=80

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

#ADDING ENVIRONMENT VARIABLES:
#Here you are referring to the previous ARG value, which has a default value of 80 but it can be modified in the run command with the modifier --build-arg DEFAULT_PORT=8000   or some other value. 
ENV PORT $DEFAULT_PORT

#USING ENVIRONMENT VARIABLES WITHIN DOCKER NEED THE "$" SIGN LIKE BELOW
EXPOSE $PORT

CMD ["npm", "start"]

