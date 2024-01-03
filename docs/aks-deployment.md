<img src="logo.jpg" width="64" />

# :walking: AKS Deployment

```bash
PREFIX="mssqldemo"
LOCATION=eastus
RESOURCEGROUP="${PREFIX}-aks-rg"

VNET_NAME="${PREFIX}-vnet"
VNET_AKS_SUBNET_NAME="aks-subnet"

AKS_NAME="${PREFIX}-aks"
AKS_NODEPOOL_NAME="${PREFIX}-nodepool-rg"

az group create --name $RESOURCEGROUP --location $LOCATION

az network vnet create --resource-group $RESOURCEGROUP --name $VNET_NAME --address-prefixes 10.114.0.0/16
az network vnet subnet create --resource-group $RESOURCEGROUP --vnet-name $VNET_NAME --name $VNET_AKS_SUBNET_NAME --address-prefixes 10.114.2.0/23
VNET_AKS_SUBNET_ID=$(az network vnet subnet show --resource-group $RESOURCEGROUP --vnet-name $VNET_NAME --name $VNET_AKS_SUBNET_NAME --query id -o tsv)

az aks create -n $AKS_NAME -g $RESOURCEGROUP --location $LOCATION --node-vm-size Standard_B4ms --network-plugin azure --network-plugin-mode overlay --pod-cidr 192.168.0.0/16 --vnet-subnet-id $VNET_AKS_SUBNET_ID
```

```bash
az aks get-credentials --resource-group $RESOURCEGROUP --name $AKS_NAME
```

## Next Step
:arrow_forward: [aks-deployment](./aks-deployment.md)
