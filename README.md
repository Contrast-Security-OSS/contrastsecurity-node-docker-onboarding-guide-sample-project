# Contrast agent deployment in Docker - Node.js

This repo is a companion to the [Contrast agent deployment in Docker - Node.js guide](https://docs.google.com/document/d/1MRixVNxp1yl5df3lqoij56gM5_XH5sJroCrW_Vt0CT4/edit?usp=sharing).

## Prerequisites

The following items should be installed in your system:

Docker

## Building

*Note: Example available in `build` script.*

```shell
docker build --rm -t juiceshop:contrast -f <path-to-dockerfile> .
```

## Running

*Note: Example available in `start` script.*

Start the container with configuration for connecting to your Contrast account.

You may use environment variables to configure Contrast:

```shell
docker run --rm -it -p 3000:3000 \
  -e CONTRAST__API__KEY=<value> \
  -e CONTRAST__API__SERVICE_KEY=<value> \
  -e CONTRAST__API__URL=<value> \
  -e CONTRAST__API__USER_NAME=<value> \
  juiceshop:contrast
```

Alternatively, you may configure Contrast with an existing Contrast YAML file by mounting the YAML file as a Docker volume at the default path (the application's base directory):

```shell
docker run --rm -it -p 3000:3000 \
  -v <path-to-yaml-file>:/juice-shop/contrast_security.yaml \
  juiceshop:contrast
```

See https://docs.contrastsecurity.com/en/configure-an-agent.html for more on configuring the Contrast agent.
