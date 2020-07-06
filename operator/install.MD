    kubectl create -f namespace.yaml
    kubectl -n argocd apply -R -f .
