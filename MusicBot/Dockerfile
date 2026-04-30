FROM node:24-alpine

RUN apk add --no-cache python3 ffmpeg yt-dlp

WORKDIR /app

COPY . .
RUN npm install --ignore-scripts && \
    mkdir -p node_modules/youtube-dl-exec/bin && \
    ln -sf /usr/bin/yt-dlp node_modules/youtube-dl-exec/bin/yt-dlp

CMD ["node", "index.js"]
