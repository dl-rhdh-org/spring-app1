# CI and CD

## Continuous Integration

Workflow: `.github/workflows/ci.yml`

- Triggers on push and pull request to `main`
- Runs `mvn test package` with Temurin 17

## Continuous Delivery

Deploy manifests live in `deploy/` and are synced by Argo CD:

- Application: `spring-app1` (OpenShift GitOps)
- Destination namespace: `spring-demos1`
- Demo image until you wire Quay push: `quay.io/openshifttest/hello-openshift:1.2.0`

After scaffolding, merge the **GitOps PR** on `rhdh-repo` so parent Application `rhdh-argocd-apps` creates the Argo CD Application (`CreateNamespace=true`).
