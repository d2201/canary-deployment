# Ingress example

## Prerequisites

- `Nginx Ingress Controller` installed on cluster
- `k8s` - I have installed `v1.24.0` - however there shouldn't be problem with lower versions

## What does ingress do?

Routes traffic from outside the cluster to services inside.

## Why nginx?

There are different ingress controllers (like [Ambassador](https://www.getambassador.io/docs/edge-stack/latest/topics/running/ingress-controller/))

I'm choosing nginx because I think it's the most popular option there.

## Tutorial

- Run `./create` - this should bootstrap entire namespace
- Testing the canary
  - Grab your cluster ip (I'll later ref it as `${CLUSTER_IP}`)
  - `curl -vvv http://${CLUSTER_IP}/app/release` - you'll get the info about release and sticky session cookie.
- After you're done with playing run `./delete` (**Warning** this only removes the created namespace, it will not uninstall nginx controller)
