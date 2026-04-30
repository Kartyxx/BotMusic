FROM node:24-alpine

RUN apk add --no-cache python3 ffmpeg

WORKDIR /app

COPY . .
RUN npm install --omit=dev

CMD ["node", "index.js"]
