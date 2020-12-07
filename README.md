# lambda-local
Lambda Local Environment

## MiniKube

```bash
minikube start && minikube dashboard
```

## Deployment

### MySQL Persistent Volume

```bash
kubectl apply -f mysql/mysql-pv.yml
```

### MySQL Service

```bash
mysql/mysql-deployment.yml
```

#### Access MySQL

```bash
kubectl run -it \
            --rm --image=mysql:5.7 \
            --restart=Never mysql-client \
            -- mysql -h mysql -ppassword
```

### LocalStack

```bash
kubectl apply -f localstack/localstack-deployment.yml
```
