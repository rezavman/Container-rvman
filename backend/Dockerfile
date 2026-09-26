FROM node:24-alpine3.22 

# create user
RUN addgroup -S app && adduser -S reza -G app

WORKDIR /app

# copy package files
COPY --chown=reza:app package*.json ./

# install deps
RUN npm install
RUN npm install -g --froce nodemon 

# copy source
COPY --chown=reza:app . .

# permissions
RUN chown -R reza:app /app

# env


# non-root user 
USER reza

# port
EXPOSE 3001

# start app
CMD ["nodemon", "index"]