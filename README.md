# argocdtixe

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: testroot
  namespace: argocd
spec:
  project: mas
  destination:
    server: https://kubernetes.default.svc
    namespace: default
  source:
    repoURL: https://github.com/tomklapiscak/argocdtest
    path: root-applications/account-root
    targetRevision: "main"
    helm:
      parameters: []
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
    syncOptions:
      - CreateNamespace=false
      - RespectIgnoreDifferences=true
```
