# Setup

## Pre-requisites

- Docker
- [Tilt](https://docs.tilt.dev/)
- Helm
- Openfaas

## Cluster Setup

- `sh scripts/01-cluster-setup.sh`
- To switch to kind cluster just do, `kubectl config use-context kind-kind`

## Openfaas

- Obtain login info for Openfaas via, `arkade info openfaas`
- Run `faas-cli login`
- Ensure that `docker login` is performed
- Replace image username in `stack.yaml` with your docker's username

# Getting Started

```
# Ensure cluster is created and running
kubectl port-forward svc/gateway -n openfaas 8080
# Run tilt
tilt up
# Run portals
yarn build && yarn start
```
