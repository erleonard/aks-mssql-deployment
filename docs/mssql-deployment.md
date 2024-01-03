<img src="logo.jpg" width="64" />

# :walking: Deploy SQL Server container on AKS

1. Create an SA password in the Kubernetes cluster. Please note that the password in the command below is for demo purposes.
```bash
kubectl create secret generic mssql --from-literal=MSSQL_SA_PASSWORD="MyC0m9l&xP@ssw0rd"
```

2. Create the persistent volume claim in Kubernetes.
```bash
kubectl apply -f ./kubernetes/mssql-pvc.yml

# Validate
kubectl describe pvc mssql-data
```

3. Deploy SQL Server:
```bash
kubectl apply -f ./kubernetes/mssql.yml

# Validate
kubectl get pod
kubectl get services
```

## Next Step
:arrow_forward: [Optional: Restore sample database](./mssql.md)
