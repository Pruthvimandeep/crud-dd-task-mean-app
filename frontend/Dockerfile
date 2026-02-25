# Stage 1: Build Angular App
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Correct Angular 15 build command
RUN npm run build -- --configuration production


# Stage 2: Serve using Nginx
FROM nginx:alpine

RUN rm -rf /usr/share/nginx/html/*

# IMPORTANT: Check your dist folder name
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
