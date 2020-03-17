##### Borrowed from Dan Wahlin - https://github.com/DanWahlin/Angular-JumpStart/blob/master/.docker/nginx.dockerfile and modified

##### Stage 1
FROM node:12.14.0 as node
LABEL author="Joseph Washington"
WORKDIR /app
COPY demo-ui/ ./
RUN npm install
COPY . .
RUN npm run build -- --prod

##### Stage 2
FROM nginx:alpine
VOLUME /var/cache/nginx
COPY --from=node /app/dist/demo-ui /usr/share/nginx/html
COPY demo-ui/.docker/config/nginx.conf /etc/nginx/conf.d/default.conf
