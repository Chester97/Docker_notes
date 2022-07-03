# Stage 1 Install and move files
FROM node:14.18.1 as install

WORKDIR /app

COPY package.json /app/
RUN npm install
COPY src /app/src
COPY public /app/public

# Stage 2 - build
FROM install AS builder

RUN npm run build

# Stage 3 - host
FROM nginx:1.17.9 AS host

COPY --from=builder /app/build /usr/share/nginx/html

CMD [ "nginx", "-g", "daemon off;" ]