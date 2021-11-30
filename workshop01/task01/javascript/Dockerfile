FROM node:17

#build - create directory and cd in
ARG APP_DIR=/app

WORKDIR ${APP_DIR}

#returns 0 if healthy and 1 for everything else
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
    CMD curl http://localhost:${PORT}/healthz || exit 1

#copy files from local into the image
ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD public public
ADD views views

#install dependencies
RUN npm ci

#run image
ENV APP_DIR=/app
ENV PORT=3000

EXPOSE ${PORT}
WORKDIR ${APP_DIR}

#run the app - ENTRYPOINT and CMD will be combined
ENTRYPOINT ["node", "main"]

# CMD ["--port", "3000"]