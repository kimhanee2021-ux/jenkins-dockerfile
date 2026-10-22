FROM nginx:alpine

ARG NODE_ENV=production

ENV NODE_ENV=${NODE_ENV}

WORKDIR /usr/share/nginx/html

RUN echo "<h1>Nginx Container ($NODE_ENV)</h1>" > index.html