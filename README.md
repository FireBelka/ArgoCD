# ArgoCD
## Create
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
(kubectl apply -f argocd-install.yaml -n argocd)
## Setup
kubectl apply -f argocd-minimal.yaml (all vars are located in argocd-vars.yaml)
## Port-forwarding
kubectl port-forward -n argocd  svc/argocd-server 8081:443
## Login
login: admin
pwt: get from secret
(kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo)
