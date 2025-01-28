# Указываем базовый образ Node.js
FROM node:18-alpine

# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем package.json и package-lock.json для установки зависимостей
COPY package.json package.json

# Устанавливаем зависимости
RUN npm install

# Копируем всё содержимое проекта в контейнер
COPY . .

# Указываем переменные окружения (например, для базы данных)
# ENV NODE_ENV=production

# Компилируем TypeScript, если используется
RUN npm run build

# Открываем порт для Strapi (по умолчанию 1337)
EXPOSE 1337

# Команда для запуска приложения
CMD ["npm", "run", "start"]