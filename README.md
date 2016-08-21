# TBus Toolchain

This is a docker image containing toolchain for development with
[tbus](https://github.com/robotalks/tbus).

## How To Use

With [hmake](https://github.com/evo-cloud/hmake),
use image `robotalks/tbus-toolchain:latest` for targets.
The following setting is required to correctly map source folder

```yaml
settings:
  docker:
    src-volume: /go/src/YOUR-GO-REPOSITORY
```

The recommended settings (take [ZuPi](https://github.com/evo-bots/zupi) as an
example):

```yaml
settings:
  docker:
    image: robotalks/tbus-toolchain:latest
    src-volume: /go/src/github.com/evo-bots/zupi
```

The tbus codegen tools are pre-installed, and all standard tbus proto files
sit in `/usr/local/include`, so no additional `-I` option is required when
invoking `tbus-proto-gen`.
