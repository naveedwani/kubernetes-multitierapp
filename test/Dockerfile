# frontend/Dockerfile

FROM node:18-alpine as build

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./
RUN npm install

COPY . .
RUN npm run build

# Serve using Nginx
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80


# build-and-load.sh
docker build -t react-frontend ./frontend
docker build -t flask-backend ./backend

kind load docker-image react-frontend --name multi-tier
kind load docker-image flask-backend --name multi-tier

