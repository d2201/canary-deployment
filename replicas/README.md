# Replicas example

## Prerequisites

- `k8s` - I have installed `v1.24.0` - however there shouldn't be problem with lower versions

## What's that?

This method is using default k8s LB, when managing the traffic to a service.
Using that knowledge we can control the amount of replicas to hint how much traffic we want in each deployment.

## Tutorial

- Run `./create` - it's creating 4 replicas of prod app and 1 replica of canary
- Run `./enter`
  - Use `curl http://app/release` - to get the current release
