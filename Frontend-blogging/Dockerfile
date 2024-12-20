FROM node:16-alpine
WORKDIR /app
RUN npm install -g serve
COPY build ./build
EXPOSE 9091
CMD ["serve", "-s", "build", "-l", "9091"]
