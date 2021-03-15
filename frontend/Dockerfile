FROM node:12-alpine3.10 as builder

WORKDIR /app

Copy["package.json", "package-lock.json", "./"]
RUN npm install

COPY ..
CMD ["npm","start"]

EXPOSE 3000

FROM nginx:alpine

EXPOSE 80

COPY --from=builder /app /usr/share/nginx/html
RUN echo 'to nginx'
