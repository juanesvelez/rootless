FROM node:14-alpine AS build-env

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 8080
RUN chown nobody:nobody -R /usr/src/app
#USER nobody
#CMD [ "node", "server.js" ]

#docker build . -t nodejs-mongo-test1
#docker run -p 3000:3000 -d nodejs-mongo-test1

FROM gcr.io/distroless/nodejs:14
COPY --from=build-env /usr/src/app /app
USER nobody
WORKDIR /app
CMD ["server.js"]