FROM node:latest AS build-step
WORKDIR /app
COPY bin .
RUN npm install
RUN npm run build

FROM nginx:latest
COPY --from=build-step /app/dist /usr/share/nginx/html
