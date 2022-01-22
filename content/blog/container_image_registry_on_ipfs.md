+++
title = "Container image registry on ipfs"

[taxonomies]
tags=["ipfs","containers"]

+++

## Existing Solutions

### IPDR

Related project [InterPlanetary Docker Registry](https://github.com/ipdr/ipdr), a cli tool to push/pull images on ipfs written in go.

> High-level overview
e <img src="/assets/blog/container_image_registry_on_ipfs/ipdr_arch.png" />
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

## Proposed direction

### Architecture

<figure>
  <img src="/assets/blog/container_image_registry_on_ipfs/arch.png" />
  <figcaption><a href="https://mermaid.live/edit/#pako:eNp1kLkOwjAMhl8l8kyF6NiBCTYmWCNVpnFpRC7lGCrg3UkJiNtDZMXf__s4QWcFQQMHj25gmy03LIezQqNhVbU8uxSGuUtKnRk6yUq9vCHti8zTQYbox_I9xYRWlcKRfMguTLo-tCa3ahcFIiP-mNRPlxcVe3f5CdXsZ6v7PF_l-mMSYbsj-Y-lb0KYgSavUYp8qdNEc4gDaeLQ5FRQj0lFDtxcMpqcwEhrIaP10PSoAs0AU7S70XTQRJ_oAa0k5uX1nbpcAbY9f_0">Edit</a></figcaption>
</figure>

In the proposed architecture the registry is an ipfs node that provider Docker Registry API so clients can push and pull images.

Usage example based on docker [registry](https://docs.docker.com/registry/configuration/):
```
docker build -t ipfs-registry .
docker run -d -p 5000:5000 --restart=always \
             -v `pwd`/config.yml:/etc/docker/registry/config.yml \
             ipfs-registry
docker pull localhost:5000/python:latest
```
