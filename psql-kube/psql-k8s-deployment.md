# create volume

kubectl create -f postgres-storage.yaml

# create config map

kubectl create -f postgres-configmap.yaml

# create pod

kubectl create -f postgres-deployment.yaml

# create service

kubectl create -f postgres-service.yaml

## Or apply the current directory (k8s/psql-kube)

kubectl apply -k .

# access psql pod

kubectl exec -it postgres-59765d88b6-tdv6t -- psql -h 10.120.0.8 -U postgres --password postgres -p 30439 postgresdb

 - postgres-59765d88b6-tdv6t = pod name
 - 10.120.0.8 = node host
 - 30439 = posgtres pod external port
