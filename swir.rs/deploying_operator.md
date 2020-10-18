# Setting up SWIR operator

We will need to create a namespace and configure permissions ...   
1. `kubectl create namespace swirop`{{execute}}  
1. `kubectl -n swirop create configmap swir-operator-config-library --from-file=./operator/books.yaml --from-file=./operator/helpdesk.yaml --from-file=./operator/magazines.yaml`{{execute}}  


1. `kubectl -n swirop create configmap swir-operator-certs-library --from-file=./certs/ca-chain.cert.pem --from-file=./certs/client.internal_grpc.swir.rs.cert.pem --from-file=./certs/client.internal_grpc.swir.rs.key.pem --from-file=./certs/server.internal_grpc.swir.rs.cert.pem --from-file=./certs/server.internal_grpc.swir.rs.key.pem`{{execute}}  

1. `kubectl -n swirop apply -f operator/service_account.yaml`{{execute}}  
1. `kubectl -n swirop apply -f operator/role.yaml`{{execute}}  
1. `kubectl -n swirop apply -f operator/role_binding.yaml`{{execute}}  

... before deploying the operator  
1. `kubectl -n swirop apply -f operator/operator.yaml`{{execute}}  

... wait for the operator to be **Running** and in **READY** state  
1. `kubectl -n swirop get po`{{execute}}



