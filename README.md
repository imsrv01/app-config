# openshift-gitops

Get admin login password for argocd

```
oc extract secret/openshift-gitops-cluster -n openshift-gitops --to=-

```

```
helm template apps/helm/guestbook

```

## Deploy app through ArgoCD

Deploy petclinic application using argocdkustomize overlay

```
kustomize build argocd/kustomize/petclinic/overlay/dev | oc apply -f -

kustomize build argocd/kustomize/petclinic/overlay/uat | oc apply -f -

kustomize build argocd/kustomize/petclinic/overlay/prod | oc apply -f -

```

Deploy guestbook application using helm chart

```
oc apply -f argocd/helm/guestbook/overlay/dev/guestbook.yaml

oc apply -f argocd/helm/guestbook/overlay/uat/guestbook.yaml

oc apply -f argocd/helm/guestbook/overlay/prod/guestbook.yaml

```

## Deploy app through Red Hat Advanced cluster manager for kubernetes (RHACM)

Deploy petclinc application using kustomize

```
oc apply -f rhacm/petclinic.yaml

```
