FROM mhart/alpine-node:latest as build
ADD . /website
WORKDIR /website
RUN npm install
RUN npm run build
RUN rm -rf node_modules
FROM mhart/alpine-node:latest
COPY --from=build /website /website
RUN npm install -g serve
WORKDIR /website
EXPOSE 5000
CMD ["npm", "run", "serve"]