# Stage 1
FROM node:14-alpine as build-stage

WORKDIR /usr/frontend-huynh
COPY FE-web-giao-xu/ .

RUN npm install

RUN npm run build

# Stage 2
FROM nginx:1.23

WORKDIR /usr/share/nginx/html

# Remove default nginx static assets
RUN rm -rf ./*

COPY --from=build-stage /usr/frontend-huynh/build /usr/share/nginx/html

CMD nginx -g 'daemon off;'


