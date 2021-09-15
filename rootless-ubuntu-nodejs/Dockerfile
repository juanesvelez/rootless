FROM ubuntu:18.04
WORKDIR /app
ADD . .
RUN apt-get update && apt-get install -y \
    nodejs \
    npm
    
RUN npm install express
EXPOSE 3000
CMD ["node", "index.js"]