<img src="logo.jpg" width="64" />

# :walking: Deploy SQL Server container on AKS

kubectl create secret generic mssql --from-literal=MSSQL_SA_PASSWORD="MyC0m9l&xP@ssw0rd"
kubectl apply -f ./kubernetes/mssql-pvc.yml

kubectl describe pvc mssql-data

kubectl apply -f ./kubernetes/mssql.yml

kubectl get pod
kubectl get services

## Next Step
:arrow_forward: [aks-deployment](./aks-deployment.md)