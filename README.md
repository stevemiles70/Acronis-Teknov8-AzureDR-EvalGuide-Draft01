# Acronis-Teknov8-AzureDR-EvalGuide-Draft01
This project repository aims to provide an evaluation guide for Disaster Recovery for Azure VMs using Acronis

## About this documentation

This documentation set will walk you through implementing a **DR Solution** for **Azure IaaS VMs** using **Acronis Cyber Clooud Disaster Recovery**  
https://www.acronis.com/en-gb/products/backup/disaster-recovery/

From your Azure IaaS nested virtualzation hosted instance of Azure Stack HCI 21 H2 you will then be able to:

* Explore the management and operational aspects of Azure Stack HCI 21 H2 
* Evaluate running workloads on Azure Stack HCI 21 H2
----
**[Click Here to jump to Deployment Steps](#deployment-Workflow)**

----

----
## Deployment Workflow

This guide will walk you through deploying a sandboxed infrastructure - the general flow will be as follows:

* **Part 1 - Deploy your Azure IaaS VM Host**: In this step, you'll create a VM in Azure using an Azure Resource Manager template. This VM will run Windows Server 2019 Datacenter, with the full desktop experience. PowerShell DSC will automatically configure this VM with the appropriate roles and features, download the necessary binaries, and configure 2 Azure Stack HCI 21H2 nodes, ready for clustering.

* **Part 2 - Configure your Azure Stack HCI 21H2 Cluster**: In this step, you'll use Windows Admin Center to deploy an Azure Stack HCI 21H2 cluster - along with a Cloud Witness, a Cluster Shared Volume, and finally, you'll register this cluster with Azure.

* **Part 3 - Integrate Azure Stack HCI 21H2 with Azure**: In this step, you'll use Windows Admin Center to register your Azure Stack HCI Cluster with Azure and explore what appears in the portal.

* **Part 4 - Explore the management and operation of your Azure Stack HCI 21H2 environment**: With your deployment completed, you're now ready to explore many of the management and operational aspects within the Windows Admin Center.

---

## Deployment Steps
This *next section* contains the steps you need to start implementing the DR solution.

*First thing though, this will require you to have the following things in place first:*

### Prerequisites
* For operational governance and control it is also **Strongly Recommended** to create a dedicated (*burner*) **Microsoft Tenant** for the purposes of this eval guide.
* This eval guide requires you to have access to an **Azure Subscription** with access to create a *Resource Group* and at least **Contributor** access on that Resource Group; it is recommended to have *Contributor* access at the **Subscription** scope level for simplicity *(Owner not required)*.
* You network connectivity shoud allow you access to reach the **Azure Portal** *https://portal.azure.com*, and allow you to open an **RDP Session** to your *ASHCI Host VM* running in Azure; 

--------

### Part 1 - Deploy your Azure VM host: 
In this step, you'll create a VM in Azure us
