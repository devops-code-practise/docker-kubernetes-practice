FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .
# Arg/env can be placed after they are called
# can only be used inside the dockerfile (can not be used on CMD instruction)
ARG DEFAULT_PORT=80
# ENV PORT 80
ENV PORT=${DEFAULT_PORT}
# WE can use env variables for EXPOSE but not build args
EXPOSE $PORT

VOLUME [ "/app/feedback" ]

CMD ["npm", "start"]
#  --env PORT = 8000 OR  --e PORT = 8000 OR ..env-file ./.env
# docker run -d --rm -p 4000:80 ..env-file ./.env --name volumed-cont -v feedback:/app/feedback -v "/mnt/d/projects/docker course/data-volumes-01-starting-setup:/app:ro" -v /app/node_modules -v /app/temp app-image:latest 