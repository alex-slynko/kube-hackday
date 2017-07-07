## Hackday


### Backend

```
# Build backend
cd dockerfiles/cats-and-dogs-backend
docker build -t c2cnetworking/cats-and-dogs-backend .
docker push c2cnetworking/cats-and-dogs-backend

# Deploy backend
kubectl create -f deployment.yml

# Expose backend as a service
kubectl create -f service.yml

# Expose backend UI as a service
kubectl create -f service-ui.yml
```

### Frontend

```
# Build frontend
cd dockerfiles/cats-and-dogs-frontend
docker build -t c2cnetworking/cats-and-dogs-frontend .
docker push c2cnetworking/cats-and-dogs-frontend

# Deploy frontend
kubectl create -f deployment.yml

# Expose frontend as a service
kubectl create -f service.yml
```

### Proxy

```
# Build proxy
cd dockerfiles/proxy
docker build -t c2cnetworking/proxy .
docker push c2cnetworking/proxy

# Deploy proxy
kubectl create -f deployment.yml

# Expose proxy as a service
kubectl create -f service.yml
```


Get the public URLs for the services:
```
minikube service cats-and-dogs-backend-ui --url
minikube service cats-and-dogs-frontend --url
minikube service proxy --url
```

Get the cluster IP for the backend:
```
kubectl get services
```

Curl the backend through the proxy:
```
curl ${PROXY_URL}/proxy/${BACKEND_CLUSTER_IP}:7007
```

kubectl create -f "/Users/pivotal/workspace/flannel/Documentation/kube-flannel.yml"

