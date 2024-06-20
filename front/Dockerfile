FROM node:16 AS build
WORKDIR /app
COPY . . 
RUN yarn install
RUN yarn build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
