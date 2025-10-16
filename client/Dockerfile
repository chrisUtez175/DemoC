#fase 1 para construir recurdos / dependencias
FROM  node:20 AS build

WORKDIR /app

COPY package*.json ./

RUN npm instal

COPY . . 

RUN npm run build
# FAse 2 : para construir la imagen

FROM  nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx","-g","daemon off;"]