#fase 0
FROM node:14.14.0-alpine
WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build
 
#fase 1
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=0 /app/build /usr/share/nginx/html
#una vez iniciado el contenedor, nginx se inicia automaticamente, no hace falta el comando run
