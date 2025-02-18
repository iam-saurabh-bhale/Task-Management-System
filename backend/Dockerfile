FROM node:slim
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
#COPY src/* .
RUN npm run lint && npm run build

FROM node:slim
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install --only=production
COPY . ./
EXPOSE 3001
ENTRYPOINT [ "node","./src/index.js" ]