<img src="logo.jpg" width="64" />

# :walking: Restore Sample Database to SQL Server (Optional)

1. Download sample database to local system
```bash
wget https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksLT2022.bak
```

2. Copy sample database to MSSQL POD 
```bash
mssql_podname=$(kubectl get po --output=jsonpath={.items..metadata.name})
fullpath=${mssql_podname}":/var/opt/mssql/data/AdventureWorksLT2022.bak"

kubectl cp AdventureWorksLT2022.bak ${fullpath}
```

3. Restore database with SQL Management Studio or Azure Data Studio
