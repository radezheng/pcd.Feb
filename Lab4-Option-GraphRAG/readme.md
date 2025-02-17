# Lab4 - 选做 - GraphRAG on Azure 快速部署
[参考repo](https://github.com/Azure-Samples/graphrag-accelerator)
https://github.com/radezheng/graphrag-accelerator-0217/blob/main/docs/DEPLOYMENT-GUIDE.md

## 准备
- 安装工具 [前置准备](https://github.com/radezheng/graphrag-accelerator-0217/blob/main/docs/DEPLOYMENT-GUIDE.md#prerequisites)
- Azure 订阅, 需要Contributor + RBAC role assignment权限 或者 Owner权限。
- 注册资源提供者(Resource Provider) 
```bash
# register providers
az provider register --namespace Microsoft.OperationsManagement
az provider register --namespace Microsoft.AlertsManagement
# verify providers were registered
az provider show --namespace Microsoft.OperationsManagement -o table
az provider show --namespace Microsoft.AlertsManagement -o table
```
- 部署环境登录Azure CLI
```bash 
# login to Azure - may need to use the "--use-device-code" flag if using a remote host/virtual machine
az login
# check what subscription you are logged into
az account show
# set appropriate subscription
az account set --subscription "<subscription_name> or <subscription id>"
```

## 部署部骤
- Git Clone 项目
```bash 
https://github.com/radezheng/graphrag-accelerator-0217
```

- 创建资源组
```bash
az group create --name <my_resource_group> --location <my_location>

# example
az group create --name rg-graphrag-accelerator-rg --location japaneast
```

### 