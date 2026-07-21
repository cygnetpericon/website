FROM node:22-bookworm

WORKDIR /app/astro

COPY astro/package*.json ./

RUN npm ci

COPY . /app

EXPOSE 4321

CMD ["npm","run","dev","--","--host","0.0.0.0"]
