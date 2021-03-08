# build stage
FROM node:12-stretch AS build
WORKDIR /app
COPY . .

RUN npm ci && npm run build

# server stage
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html