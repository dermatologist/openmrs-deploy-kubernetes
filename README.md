# Deploy OpenMRS on Kubernetes

## Experimental based on

* [Using Persistent Disks with WordPress and MySQL](https://cloud.google.com/kubernetes-engine/docs/tutorials/persistent-disk)
* [djazayeri/openmrs-contrib-gcptest](https://github.com/djazayeri/openmrs-contrib-gcptest)

## Steps

### STEP 1. Create your PersistentVolumes and PersistentVolumeClaims

```
kubectl apply -f mysql-volumeclaim.yaml
kubectl apply -f openmrs-volumeclaim.yaml
```

Check

```
kubectl get pvc

```


### STEP 2. Create MySQL password as a secret

```
kubectl create secret generic mysql --from-literal=password=YOUR_PASSWORD

```

### STEP 3. Deploy MySQL 

```
kubectl create -f mysql.yaml
```


Check

```
kubectl get pod -l app=mysql

```

### STEP 4. Create MySQL service

```
kubectl create -f mysql-service.yaml
```


Check

```
kubectl get service mysql

```


### STEP 5. Deploy OpenMRS

```
kubectl create -f openmrs.yaml
```


Check

```
kubectl get pod -l app=openmrs
```


### STEP 6. Create openmrs service

```
kubectl create -f openmrs-service.yaml
```


Check external IP

```
kubectl get svc -l app=openmrs
```


### STEP 7. Access your site

```
<EXTERNAL IP>/openmrs
```

### STEP 8. Clean Up

```
kubectl delete service openmrs
kubectl delete service mysql
kubectl delete pvc openmrs-volumeclaim
kubectl delete pvc mysql-volumeclaim
```

## Author

Bell Eapen (McMaster U)
