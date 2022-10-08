# Service mesh example

## Prerequisites

- `Traefik` installed on any namespace
- `k8s` - I have installed `v1.24.0` - however there shouldn't be problem with lower versions

## What's a service mesh?

https://www.redhat.com/en/topics/microservices/what-is-a-service-mesh

## How to choose one?

It should be compliant with this spec https://smi-spec.io/.
For my case and some entry experience I've chosen `Traefik` https://doc.traefik.io/traefik-mesh.

## Tutorial

- Run `./create` - this should bootstrap the namespace and add necessary apps
- Run `./enter` - this gets you into the client pod which has the necessary tooling
- API interface:
  - Get splitted traffic - `curl app.service-mesh-canary.maesh/release` - Call this method multiple times
  - Get prod app - `curl prod-app-service.service-mesh-canary.maesh/release` or `curl prod-app-service/release` (First method is through service mesh, second method is through k8s dns)
  - Get canary app `curl canary-app-service.service-mesh-canary.maesh/release` or `curl canary-app-service/release`
- After you're done with playing run `./delete` (**Warning** this only removes the created namespace, it will not uninstall traefik)
