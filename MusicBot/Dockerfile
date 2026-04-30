FROM node:24-alpine

RUN apk add --no-cache python3 ffmpeg yt-dlp

WORKDIR /app

COPY . .
RUN npm install --ignore-scripts

CMD ["node", "index.js"]
