# frontend/Dockerfile
FROM node:20-alpine AS build
WORKDIR /app
COPY vue-app/package*.json ./
RUN npm install
COPY vue-app/. .
RUN npm run build

# Etap produkcyjny
FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80