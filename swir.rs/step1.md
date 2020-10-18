### Setting up operator
`kubectl create namespace operator-ns`{{execute}}
`kubectl -n operator-ns create configmap swir-operator-config --from-file=./books.yaml --from-file=./helpdesk.yaml --from-file=./magazines.yaml` {{execute}}

