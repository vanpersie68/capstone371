FROM node:16.18.0 AS build
WORKDIR /frontend
COPY frontend .
ENV VUE_APP_SERVER http://170.64.174.169/api/
RUN npm install --legacy-peer-deps

FROM nginx:latest
COPY ./docker/vue/nginx.conf /etc/nginx/conf.d/cs371.conf
COPY --from=build /frontend/dist /usr/share/nginx/html
