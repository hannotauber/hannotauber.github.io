+++
title = "Container image registry on ipfs"

[taxonomies]
tags=["ipfs","containers"]

+++

## Existing Solutions

### IPDR

Related project [InterPlanetary Docker Registry](https://github.com/ipdr/ipdr), a cli tool to push/pull images on ipfs written in go.

> High-level overview
> <img src="/blog/ipdr_arch.png" />
> License [MIT](https://github.com/ipdr/ipdr/blob/master/LICENSE)

```
$ ipdr push example/helloworld
$ ipdr pull /ipfs/QmagW4H1uE5rkm8A6iVS8WuiyjcWQzqXRHbM3KuUfzrCup
```

`ipdr` cli tool acts as a middle man to integrate 2 services:
- A container registry.
- IPFS as filesystem.

It includes also support with a local server as a docker registry but does not seem to work only for `pull`.  Documentation compatibility states [Docker Registry HTTP API V2](https://docs.docker.com/registry/spec/api/#docker-registry-http-api-v2), so anyone could use the software _on top_ of registry as cli _or_ along internal implementation of registry `pulls` for convenience.

This solution serves the purpose of using ipfs as the filestorage of container images for local usage development.


## Appendix

### Graphs

1. Architecture (
```
graph LR
    podman -->|push/pull| registry
    docker -->|push/pull| registry
    registry --layers--> ipfs_network
    ipfs_network --layers--> registry
```

