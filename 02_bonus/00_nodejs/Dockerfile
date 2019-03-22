FROM node:8

WORKDIR /app
ENV NODE_ENV production

COPY index.js /app

RUN npm install --production

EXPOSE 80 8080

CMD ["node", "index.js"]
