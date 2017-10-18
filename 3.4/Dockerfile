FROM node:8.6-alpine

RUN mkdir /truffle
RUN chown node /truffle
WORKDIR /truffle

RUN apk add --no-cache git
RUN apk add -t .gyp --no-cache python g++ make \
    && npm install -g truffle@3.4.11 \
    && npm install -g ethereumjs-testrpc \
    && apk del .gyp
