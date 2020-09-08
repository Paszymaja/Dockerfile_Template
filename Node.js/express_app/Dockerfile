FROM node:latest as build-env
ADD . /app
WORKDIR /app
RUN npm install

FROM gcr.io/distroless/nodejs:latest
COPY --from=build-env /app /app
WORKDIR /app
EXPOSE 8080
CMD ["nodemon", "app.js"]