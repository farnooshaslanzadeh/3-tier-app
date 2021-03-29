FROM node:12-alpine3.10 as builder
  
WORKDIR /usr/src/app

COPY ["package.json", "package-lock.json", "./"]
RUN npm install
COPY . .
RUN npm run build


FROM nginx

EXPOSE 80

COPY --from=builder /usr/src/app/build /usr/share/nginx/html
