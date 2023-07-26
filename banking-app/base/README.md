# Demo Banking App

## Important Notes
This directory contains the base configurations for the banking-app.

- Do not add any modified VirtualServices, DestinationRules, etc to this base config directory.
- Any such modifications should be done in another directory that is a sibling to this directory.
- It follows the [Istio guidelines](https://istio.io/latest/docs/ops/deployment/requirements/) and has proper app and version labels for all deployments. 
- Note the naming convention. Each file is named `{app-name}-{kind-shortname}`.
  - Use `kubectl api-resources` to see the shortname of each kind.
  - If a shortname is not available, use the full name in lowercase.
- Note that a sample banking-app namespace is provided with `istio-injection=enabled`. None of the manifests should have a namespace set in the manifest itself unless otherwise required (for e.g. RBAC). Such manifests should be kept separate and documented appropriately.

## Getting Started

1. `kubectl apply -f banking-app-ns.yaml`
2. `kubectl apply -n banking-app -f k8s/`
3. `kubectl apply -n banking-app -f istio/`
