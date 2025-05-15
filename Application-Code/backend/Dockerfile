FROM node:14 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

FROM node:14-slim

WORKDIR /app

COPY --from=build /app .

EXPOSE 8080

CMD ["node", "index.js"]

