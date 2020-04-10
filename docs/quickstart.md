# Quick Start

Fork and clone
```bash
mkdir -p $GOPATH/src/sigs.k8s.io
cd $GOPATH/src/sigs.k8s.io

# fork https://github.com/kubernetes-sigs/application
# clone
GITHUBID=<githubid>
git clone git@github.com:${GITHUBID}/application.git $GOPATH/src/sigs.k8s.io/application
```

Run locally
```bash
# create local cluster
make e2e-setup

# install CRD
make deploy-crd

# run locally
make run

# tear down
make e2e-cleanup
```

Run against cluster
```bash
# The default image is `gcr.io/$(shell gcloud config get-value project)/kube-app-manager`
# to use different image edit VERSION-DEV file

# build docker image
make docker-build
make docker-push

# deploy to cluster
make deploy

# deploy example
make deploy-wordpress
```
