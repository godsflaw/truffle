FROM node:10-alpine

RUN mkdir /truffle
RUN chown node /truffle
WORKDIR /truffle

RUN apk add -t .gyp --no-cache bash git python g++ make \
    && npm config set unsafe-perm true \
    && npm install -g truffle@4.1.14 \
    && npm install -g ganache-cli \
    && npm install -g zos
