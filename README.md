# ArgoCD
## Create
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
(kubectl apply -f argocd.yaml -n argocd)
## Login
login: admin
pwt: get from secret
(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo)
