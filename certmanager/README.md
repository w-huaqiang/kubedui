### OutOfsync
refer https://argoproj.github.io/argo-cd/user-guide/diffing/

```bash
kubectl edit configmap/argocd-cm -n argocd
```

> add

```
date:
  resource.customizations: |
    admissionregistration.k8s.io/MutatingWebhookConfiguration:
      ignoreDifferences: |
        jsonPointers:
        - /webhooks/0/clientConfig/caBundle
    admissionregistration.k8s.io/ValidatingWebhookConfiguration:
      ignoreDifferences: |
        jsonPointers:
        - /webhooks/0/clientConfig/caBundle
```
