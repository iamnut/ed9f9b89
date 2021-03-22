FROM node:lts-stretch-slim
LABEL maintainer="public@iamnut.com"
SHELL ["/bin/bash", "-c"]

WORKDIR /app

EXPOSE 5000
ENV HOST=0.0.0.0 \
    PORT=5000

COPY . /app
RUN npm install

HEALTHCHECK --interval=5s --timeout=5s CMD curl -sf http://localhost:5000/healthz || exit 1
CMD ["node", "server.js"]