FROM node:10-alpine

RUN mkdir /truffle
RUN chown node /truffle
WORKDIR /truffle

RUN apk add -t .gyp --no-cache git python g++ make \
    && npm install -g truffle@4.1.13 \
    && npm install -g ganache-cli
