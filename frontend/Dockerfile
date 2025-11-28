# Stage 1 - Build Angular
FROM node:18 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build --prod

# Stage 2 - NGINX
FROM nginx:alpine

COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
COPY ./nginx.conf /etc/nginx/nginx.conf

