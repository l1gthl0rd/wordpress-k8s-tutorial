# Deployment

## windows setup

```powershell
# start minikube so you have a kubernetes cluster
minikube start
# update enviroment to build container image
& minikube -p minikube docker-env --shell powershell | Invoke-Expression
# build container image
docker build app -t flask-api
# deploy into cluster
kubectl apply -f ./
```

## mysql setup

```powershell
# start mysql console
kubectl run -it --rm --image=mysql:5.6 --restart=Never mysql-client2 -- mysql -h mysql -pmine
```

```sql
-- copy me into mysql console
CREATE DATABASE flaskapi;
USE flaskapi;
CREATE TABLE users(user_id INT PRIMARY KEY AUTO_INCREMENT, user_name VARCHAR(255), user_email VARCHAR(255), user_password VARCHAR(255));
```
