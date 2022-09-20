# Helm Cheat Sheet

Most common `helm` commands

```sh
# repo 
helm repo list # list existing repo
helm repo add bitnami https://charts.bitnami.com/bitnami # add repo (bitnami)
helm repo update # stay up to date
helm repo remove bitnami # remove repo

# search
helm search hub wordpress # search artifact hub
helm search repo bitnami # search repo

# install
helm install hello-wordpress bitnami/wordpress # install with specified name
helm install bitnami/wordpress --generate-name # install with name auto-generated
helm install foo path/to/foo # install an upacked chart directory
helm install bitnami/wordpress --generate-name --dry-run --debug # check generated manifests of a release without installing

# install: override any of these settings
echo '{mariadb.auth.database: user0db, mariadb.auth.username: user0}' > values.yaml
helm install -f values.yaml bitnami/wordpress --generate-name

# show
helm show values bitnami/wordpress # too see what options are configurable
helm show chart bitnami/wordpress # display information about a chart

# upgrade/rollback
helm upgrade -f hello.yaml hello-wordpress bitname/wordpress # upgrade release
helm rollback hello-wordpress 1 # roll back to a previous release, a release version is an incremental revision (incremented by 1)

# uninstall 
helm uninstall happy-wordpress # uninstall a release

# creating your own charts
helm create my-workflow
helm package my-workflow 
helm install my-workflow ./my-workflow-0.1.0.tgz

# pull 
helm pull 0.1.0 wordpress # download a chart with release
helm pull --untar bitnami/wordpress # download a chart from a repository and (optionally) unpack it in local directory

# misc
helm list # list release (or helm ls)
helm status hello-wordpress # current state of your release
helm get values hello-wordpress # see values
helm history [RELEASE] # to see revision numbers for a certain release
helm template bitnami/wordpress --debug # to test rendering chart templates locally
```
