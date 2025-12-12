FROM node:20-alpine

LABEL org.opencontainers.image.source=https://github.com/qa-tech-training/qadevoprac3-capstone-lab-starter

WORKDIR /app

# TODO: add the instructions needed to copy the package.json, install dependencies, and copy the server.js file
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

CMD ["node", "server.js"]