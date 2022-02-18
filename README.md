# GithubGitOps
GitOps ArgoCD

The Key GitOps Principles:

    The entire system (infrastructure and applications) is described declaratively.
    The canonical desired system state is versioned in Git.
    Changes approved are automated and applied to the system.
    Software agents ensure correctness and alert on divergence.

Some Pros of GitOps:

    Faster deployments
    Safer deployments
    Easier rollbacks
    Straightforward auditing
    Better traceability
    Eliminating configuration drift


Install ArgoCD

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Adquire the password. The user name is admin

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

Download the repository and apply the configuration

```
kubectl apply -f application.yaml 
```


