FROM node:12-stretch AS build

WORKDIR /app

COPY ./client .
COPY .env .

RUN npm ci && npm run build

FROM nginx:1.17

COPY --from=build /app/dist /usr/share/nginx/html

COPY ./client/locales /usr/share/nginx/html/locales