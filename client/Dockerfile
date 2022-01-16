FROM node:14.18.3-alpine3.14 as builder
WORKDIR '/app'
COPY . .
RUN npm install
RUN npm run build

FROM nginx:1.21.5 as final
EXPOSE 3000
COPY --from=builder /app/build /usr/share/nginx/html