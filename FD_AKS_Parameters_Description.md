# Cloud Competence Center - Feature Description – Azure Kubernetes Service (AKS) v1902 - Parameters Description

## Content

1. [Overview](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+-+Overview)
2. [Installation](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+-+Installation)
3. [Parameters](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+-+Parameters)
    - 3.1. [Parameters Description](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+-+Parameters+-+Description)
        - 3.1.1. Microsoft.Sql CCC template reference
        - 3.1.2. Property values
    - 3.2. [Parameters Baseline](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+-+Parameters+-+Baseline)
        - 3.2.1. Introduction
        - 3.2.2. Baseline parameter file
4. [Security](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+Security)
5. [Service Management](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+Service+Management)
6. [Examples](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+Examples)
7. [Example pipeline](https://confluence.dev.rabobank.nl/display/Azure/AKS+%28v1902%29+Example+Pipeline)
8. [Microsoft AKS documentation](https://docs.microsoft.com/en-us/azure/aks/)

## 3. Parameters

### 3.1. Parameters Description

#### 3.1.1. Microsoft.ContainerService CCC template reference

To use the CCC template to deploy an Azure Kubernetes Service cluster, use a parameter file in the following format. See paragraph 3.1.2. the following paragraph for details on the property values.

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "resourceName": {
            "value": "string"
        },
        "location": {
            "value": "string"
        },
        "kubernetesVersion": {
            "value": "string"
        },
        "dnsPrefix": {
            "value": "string"
        },
        "agentCount": {
            "value": integer
        },
        "agentVMSize": {
            "value": "string"
        },
        "agentOsDiskSizeGB": {
            "value": integer
        },
        "agentMaxPods": {
            "value": integer
        },
        "agentOsType": {
            "value": "string"
        },
        "linuxAdminUsername": {
            "value": "string"
        },
        "linuxSshPublicKeyData": {
            "value": "string"
        },
        "armIntegrationServicePrincipalId": {
            "value": "string"
        },
        "armIntegrationApplicationId": {
            "value": "string"
        },
        "armIntegrationApplicationSecret": {
            "value": "string"
        },
        "aadIntegration": {
            "value": boolean
        },
        "aadIntegrationClientApplicationId": {
            "value": "string"
        },
        "aadIntegrationServerApplicationId": {
            "value": "string"
        },
        "aadIntegrationServerApplicationSecret": {
            "value": "string"
        },
        "aadIntegrationTenantId": {
            "value": "string"
        },
        "serviceEndpoints": [
            {
                "service": "string",
                "locations": [ "string" ]
            }
        ],
        "serviceCidr": {
            "value": "string"
        },
        "dnsServiceIP": {
            "value": "string"
        },
        "dockerBridgeCidr": {
            "value": "string"
        }
    }
}
```

#### 3.1.2. Property values

The following tables describe the values you need to set in the schema.

##### 3.1.2.1. Parameters

| Name | Type | Required | May be empty | Resource type | API level | Value |
| --- | --- | --- | --- | --- | --- | --- |
| resourceName| string| yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#microsoftcontainerservicemanagedclusters-object) | 2018-03-31 | The name of the Managed Cluster resource and a prefix for related services |
| location | string | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#microsoftcontainerservicemanagedclusters-object) | 2018-03-31 | The location of AKS resource. |
| kubernetesVersion | string | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusterproperties-object) | 2018-03-31 | The version of Kubernetes. |
| dnsPrefix | string | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusterproperties-object) | 2018-03-31 | DNS prefix to use with hosted Kubernetes API server FQDN. |
| agentCount | integer | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteragentpoolprofile-object) | 2018-03-31 | Number of agents (VMs) to host docker containers. Allowed values must be in the range of 1 to 100 (inclusive). |
| agentVMSize | enum | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteragentpoolprofile-object) | 2018-03-31 | Size of agent VMs. |
| agentOsDiskSizeGB | integer | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteragentpoolprofile-object) | 2018-03-31 | OS Disk Size in GB to be used to specify the disk size for every agent in this master/agent pool. If you specify 0, it will apply the default osDisk size according to the vmSize specified. |
| agentMaxPods | integer | yes | no |[Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteragentpoolprofile-object) | 2018-03-31 | Maximum number of pods that can run on an agent. |
| agentOsType | string | no| no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteragentpoolprofile-object) | 2018-03-31 | The type of operating system on the nodes. At this moment only `Linux` supported. |
| linuxAdminUsername | string | no | no |[Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#containerservicelinuxprofile-object) | 2018-03-31 | The administrator username to use for the Linux agents. |
| linuxSshPublicKeyData | object | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#containerservicelinuxprofile-object) | 2018-03-31 | Certificate public key used to authenticate with the Linux agents using SSH. The certificate must be in PEM format with or without headers.  If not used, use "" |
| armIntegrationServicePrincipalId | string | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusterserviceprincipalprofile-object) | 2018-03-31 | The ID of the service principal. (Information about a service principal identity for the cluster to use for manipulating Azure APIs.) |
| armIntegrationApplicationId | string | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusterserviceprincipalprofile-object) | 2018-03-31 | The application id linked to the service principal. (Information about a service principal identity for the cluster to use for manipulating Azure APIs.) |
| armIntegrationApplicationSecret | string | no | yes | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusterserviceprincipalprofile-object) | 2018-03-31 | The secret password associated with the service principal in plain text. (Information about a service principal identity for the cluster to use for manipulating Azure APIs.) |
| aadIntegration | boolean | yes | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#template-format) | 2018-03-31 | Switch to indicate wheter or not Kubernetes RBAC is enabled. When true then Azure AD integration is enabled as well. |
| aadIntegrationClientApplicationId | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteraadprofile-object) | 2018-03-31 | Azure AD Application ID of the AAD integration client component. |
| aadIntegrationServerApplicationId | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteraadprofile-object) | 2018-03-31 | Azure AD Application ID of the AAD integration server component. |
| aadIntegrationServerApplicationSecret | string| no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteraadprofile-object) | 2018-03-31 | Secret for the application ID of the AAD integration server component. |
| aadIntegrationTenantId | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#managedclusteraadprofile-object) | 2018-03-31 | The Azure AD tenant ID where the AAD integration Application IDs and Service Principals are part of. |
| serviceEndpoints | array | yes | no | [Microsoft.Network/virtualNetworks](https://docs.microsoft.com/en-us/azure/templates/microsoft.network/2018-11-01/virtualnetworks#subnetpropertiesformat-object) | 2018-11-01 | Array which may contain the Service Endpoints which need to be enabled. See 3.1.2.2. serviceEndpoint array. Note if not used, use []. If you want to add a serviceendpoint use this format:  "serviceEndpoints": { "value": [ "Microsoft.Storage"] }| 
| serviceCidr | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#containerservicenetworkprofile-object) | 2018-03-31 | An IP address assigned to the Kubernetes DNS service. It must be within the Kubernetes service address range specified in serviceCidr. |
| dnsServiceIP | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#containerservicenetworkprofile-object) | 2018-03-31 | An IP address assigned to the Kubernetes DNS service. It must be within the Kubernetes service address range specified in serviceCidr. |
| dockerBridgeCidr | string | no | no | [Microsoft.ContainerService/managedClusters](https://docs.microsoft.com/en-us/azure/templates/microsoft.containerservice/2018-03-31/managedclusters#containerservicenetworkprofile-object) | 2018-03-31 | A CIDR notation IP range assigned to the Docker bridge network. It must not overlap with any Subnet IP ranges or the Kubernetes service address range. |
||

##### 3.1.2.2. serviceEndpoint array

| Name | Type | Required | May be empty | Resource type | API level | Value |
| --- | --- | --- | --- | --- | --- | --- |
| service | string | no | yes | [Microsoft.Network/virtualNetworks](https://docs.microsoft.com/en-us/azure/templates/microsoft.network/2018-11-01/virtualnetworks#serviceendpointpropertiesformat-object) | 2018-11-01 | The type of the endpoint service. |
| locations | array | no | yes | [Microsoft.Network/virtualNetworks](https://docs.microsoft.com/en-us/azure/templates/microsoft.network/2018-11-01/virtualnetworks#serviceendpointpropertiesformat-object) | 2018-11-01 | A list of locations (Azure Regions). - string |
||
