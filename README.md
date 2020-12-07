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

#### Shell Access

```bash
kubectl exec --stdin \
        --tty $(kubectl get pods -l app=mysql | grep ^mysql | awk '{print $1}') \
	-- /bin/bash
```

### LocalStack

```bash
kubectl apply -f localstack/localstack-deployment.yml
```
