FROM node:14 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install 

COPY . .

RUN npm run build

FROM node:14-slim

WORKDIR /app

COPY --from=build /app .

EXPOSE 3000

CMD ["npm", "start"]
