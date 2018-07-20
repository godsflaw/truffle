# truffle
Docker image of Truffle - simple development framework for Ethereum

# Supported tags and respective `Dockerfile` links

* `4.1`, `latest` [(Dockerfile)](https://github.com/godsflaw/truffle/blob/master/4.1/Dockerfile)

# Running ganache with `ganache`

Make sure that correct host is set in `truffle.js`.

It MAY look like this:

v2:

```js
module.exports = {
  rpc: {
    host: process.env.GANACHE__HOST || "localhost",
    port: 8545
  }
};
```

v3

```js
module.exports = {
  networks: {
    development: {
      host: process.env.GANACHE_HOST || "localhost",
      port: 8545,
      network_id: "*"
    }
  }
};
```

Run `ganache` server instance:

```bash
docker run --rm -d --name ganache -p 8545 godsflaw/ganache:latest
```

And then run `truffle` tests:

```bash
docker run --rm -v "${PWD}:/usr/src/app" --link ganache -e "GANACHE_HOST=ganache" godsflaw/truffle:latest test
```
