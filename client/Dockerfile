# require Dockerfile in order to make custom image

# FROM baseImage
# WORKDIR /the/workdir/path
# COPY source dest
# RUN command
# COPY source dest
# RUN command
# CMD [ "executable" ]

FROM node:20
WORKDIR /user/src/app 
# WORKDIR -> where you want to store source code of this image in docker locally (e.g) /user/src/app   or  /user or  /app 
COPY package*.json ./
# execute the below command only if their is changes in the package*.json file (it compares the package*.json file with the previously cached package*.json)
RUN npm install
COPY . .
# . . means copy all the file or folders (except those who all are present in the .dockerignore)  from the current directory(containing this Dockerfile) and paste it inside of app folder of this (/user/src/app)
#.dockerignore is similar to .gitignore
RUN npm run build
CMD [ "npm" , "start" ]