FROM node:18

# Clean and update, then install Python, ffmpeg, and yt-dlp
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y python3 python3-pip ffmpeg && \
    pip3 install --no-cache-dir yt-dlp

WORKDIR /app
COPY . .

RUN npm install

EXPOSE 8080

CMD ["node", "index.js"] 
