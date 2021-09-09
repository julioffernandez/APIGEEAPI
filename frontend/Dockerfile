### STAGE 1: Build ###
FROM node:12.7-alpine AS node
WORKDIR /app
COPY package.json package-lock.json 
COPY . .
RUN npm install
RUN npm run build
### STAGE 2: Run ###
FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=node /app/dist/Frontend /usr/share/nginx/html