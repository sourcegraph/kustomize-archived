# Sourcegraph Kustomize

TODO

## Overlays

An overlay specifies customizations for a base directory of Kubernetes manifests, in this case the [base/](https://sourcegraph.com/github.com/sourcegraph/deploy-sourcegraph@master/-/tree/base) directory in the [deploy-sourcegraph repository](https://sourcegraph.com/github.com/sourcegraph/deploy-sourcegraph@master).

Each overlay is created with different kustomize components that are located inside the components directory.

## Components

TODO

## How to use

### Build overlay

Run the following command in the root of this repository. Replace `$OVERLAY` with the name of the overlay.

```bash
# example: kubectl apply -k overlays/minikube > .overlay_output.yaml
kustomize build overlays/$OVERLAY > .overlay_output.yaml
```

### Apply overlay

Run the following command in the root of this repository. Replace `$OVERLAY` with the name of the overlay.

```bash
# example: kubectl apply -k overlays/minikube
kubectl apply -k overlays/$OVERLAY
# or
# example: kustomize build overlays/minikube | kubectl apply -f -
kustomize build overlays/$OVERLAY | kubectl apply -f -
```
