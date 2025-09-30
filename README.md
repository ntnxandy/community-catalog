# community-catalog

apply this in your cluster
NKP version 2.15 

```
nkp create catalog demo-apps-catalog -w kommander-workspace --branch main --url https://github.com/ntnxandy/community-catalog.git
```

ab NKP 2.16

```
nkp create catalog-application -w komander-workspace --url https://github.com/ntnxandy/community-catalog.git
```

```
apiVersion: source.toolkit.fluxcd.io/v1
kind: GitRepository
metadata:
  name: community-catalog
  namespace: kommander
  labels:
    kommander.d2iq.io/gitapps-gitrepository-type: catalog
    kommander.d2iq.io/gitrepository-type: catalog
    kommander.d2iq.io/workspace-default-catalog-repository: "true"
spec:
  interval: 1m0s
  ref:
    branch: main
  timeout: 1m0s
  url: https://github.com/ntnxandy/community-catalog.git
```
