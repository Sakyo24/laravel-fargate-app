# FROM node:16-alpine as node
FROM nginx:1.20-alpine
LABEL maintainer="ucan-lab <yes@u-can.pro>"
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

ENV TZ=UTC

RUN apk update && \
  apk add --update --no-cache --virtual=.build-dependencies g++  && \
  apk add --no-cache nodejs npm

# node command
# COPY --from=node /usr/local/bin /usr/local/bin
# npm command
# COPY --from=node /usr/local/lib /usr/local/lib
# yarn command
# COPY --from=node /opt /opt
# nginx config file
COPY ./infra/docker/nginx/*.conf /etc/nginx/conf.d/

COPY ./backend/public /work/backend/public

WORKDIR /work/backend
