# Deprek8ion 🕵️‍

[![CircleCI](https://circleci.com/gh/swade1987/deprek8ion.svg?style=svg)](https://circleci.com/gh/swade1987/deprek8ion)
[![CloMonitor](https://img.shields.io/endpoint?url=https://clomonitor.io/api/projects/open-gitops/open-gitops/badge)](http://localhost:3000/projects/open-gitops/open-gitops)

A set of rego policies to monitor Kubernetes APIs deprecations.

The Kubernetes API deprecations can be found using <https://relnotes.k8s.io/?markdown=deprecated>.

## Docker image

The docker container contains the most recent version of [conftest](https://github.com/instrumenta/conftest) as well as the policies at `/policies`.

Image tags can be found at [https://eu.gcr.io/swade1987/deprek8ion](https://eu.gcr.io/swade1987/deprek8ion)

## Artifact Hub

The policies are also available at [https://artifacthub.io/packages/opa/deprek8ion/deprek8ion](https://artifacthub.io/packages/opa/deprek8ion/deprek8ion).

## Example usage

An example of how to use the docker container can be seen below:

```sh
docker run --rm --name demo -v $(pwd)/demo:/demo eu.gcr.io/swade1987/deprek8ion:1.1.17 /demo/ingress.yaml
```

Or directly pipe some resources into the container:

```sh
cat ./demo/ingress.yaml | docker run --rm -i eu.gcr.io/swade1987/deprek8ion:1.1.17 -
```
