FROM node:24-alpine

RUN apk add --no-cache python3 ffmpeg

WORKDIR /app

COPY . .
RUN FFMPEG_STATIC=0 npm install

CMD ["node", "index.js"]
