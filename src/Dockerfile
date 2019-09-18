# install all packages

FROM node:alpine AS builder

WORKDIR '/app'
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
#port mapping
EXPOSE 80 
COPY --from=builder /app/build /usr/share/nginx/html


