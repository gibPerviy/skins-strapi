# Указываем базовый образ Node.js
FROM node:18-alpine as build

# WORKDIR /app
COPY package.json package.json
RUN npm install
COPY . .
RUN npm run build

FROM nginx:stable-alpine
COPY --from=build /dist /usr/share/nginx/html
COPY --from=build nginx.conf /etc/conf.d/default.conf
EXPOSE 3000

# Команда для запуска приложения
CMD [ "nginx", "-g", "daemon off;" ]