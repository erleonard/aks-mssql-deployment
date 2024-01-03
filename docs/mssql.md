<img src="logo.jpg" width="64" />

# :walking: Restore Sample Database to SQL Server
Optional step

```bash
wget https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksLT2022.bak
```

aaa
```bash
mssql_podname=$(kubectl get po --output=jsonpath={.items..metadata.name})
fullpath=${mssql_podname}":/var/opt/mssql/data/AdventureWorks2014.bak"

kubectl cp AdventureWorksLT2022.bak ${fullpath}
```

## Next Step
:arrow_forward: [aks-deployment](./aks-deployment.md)

# download
https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=data-studio#download-backup-files
# restore
https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=data-studio#restore-to-sql-server
