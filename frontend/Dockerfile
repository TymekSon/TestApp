# frontend/Dockerfile
FROM node:20-alpine AS build
WORKDIR /app

# Kopiuj package.json i package-lock.json
COPY vue-app/package*.json ./
RUN npm install

# Kopiuj resztę (w tym index.html z korzenia!)
COPY vue-app/. .

# Buduj
RUN npm run build

# Serwuj przez nginx
FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80