# Acronis-Teknov8-AzureDR-EvalGuide-Draft01
This project aims to provide an evaluation guide for Disaster Recovery for Azure VMs using Acronis

## About this documentation

This documentation set will walk you through implementing a **DR Solution** for **Azure IaaS VMs** using **Acronis Cyber Cloud Disaster Recovery**  
https://www.acronis.com/en-gb/products/backup/disaster-recovery/

From your implemented DR scenario you will then be able to:

* Explore the management and operational aspects of DR using the *Acronis Cyber protect console*

----
**[Click Here to jump to Deployment Steps](#deployment-Workflow)**

----

## What is Acronis Cyber Disaster Recovery?

**Effortless cloud-based Cyber Disaster Recovery for Acronis Cyber Protect**

Acronis Cyber Disaster Recovery Add-on is built on top of Acronis Cyber Backup and ensures quick failover of your critical workloads to the cloud, improving your business continuity capabilities with ease. Gain instant data availability of all critical workloads no matter what kind of disaster strikes. 

**Disaster recovery (DR) on top of your backups** 
Add disaster recovery to your backups in a matter of seconds, utilizing the same agent, web console, backup storage, and cloud infrastructure. Acronis Cyber Disaster Recovery Add-on, on top of Acronis Cyber Backup Cloud, provides all-in-one backup, disaster recovery, and advanced ransomware protection.

**Isolated testing environment** 
Ensure process availability with non-disruptive failover testing. Keep all backed up servers and applications running continuously and in line with your DR plan by starting recovery servers in Acronis Cloud’s isolated testing environment, with no impact on your production network.

**Intuitive web-based console**
Set up, add, and configure the cloud-based recovery server with just a few clicks. The intuitive, touchfriendly, web-based console ensures IT generalists
can easily implement most disaster recovery activities, including network configuration, failover testing, and failback.

*Read more here:* https://www.acronis.com/en-gb/products/backup/disaster-recovery/

### What is a disaster recovery solution?
Disaster recovery solutions allow companies to quickly resume business-critical workloads after cyber-attacks, natural disasters or server failures. The disaster recovery process normally involves a separate physical or cloud site to restore data. Every disaster recovery solution aims to help businesses operate as usual. Since business continuity depends on high availability, disaster recovery strategies depend on RTOs and RPOs.

### Where should I back up my data to perform disaster recovery?
To be able to failover your critical workloads, you should back up your data to Acronis Cloud Storage.... As the disaster occurs, your workload will be failed-over to the //cloud// server running in the Acronis Cyber Disaster Recovery Storage.

### Can I backup data from Azure VMs ?
**Yes** you can protect your **Azure IaaS VMs** with this **Acronis Disaster Recovery Solution**; this will allow your VM to failover to the //cloud// instance running in the Acronis Cyber Cloud platform and can be failed-back when required; A S2S VPN will be required to provide connectivity between the two sites (Azure and Acronis Platforms) to enable protection.

-----------
## Acronis Training Resources

**Acronis You Tube Channel**
https://www.youtube.com/playlist?list=PLJbh8iM59BMfWvpAKRCtejTKokGPItdIg

* Acronis Data Cloud Technical Training: 1.2.1. Acronis Data Cloud Basics https://youtu.be/nWp73LyvsUQ
* Acronis Data Cloud Technical Training: 2.2.1. Backup service basics https://youtu.be/XzaW51jvnS8
* Acronis Data Cloud Technical Training: 2.2.2. Acronis Backup Cloud Implementation models https://youtu.be/0XmLR4P5ADY
* Acronis Data Cloud Technical Training: 2.2.5. Acronis Backup Cloud Supported Platforms https://youtu.be/ml1wD7yVFUs

**DR specific resources**
* Introducing Acronis Disaster Recovery Cloud https://youtu.be/cnVLKrcd6JA
* Acronis Data Cloud Technical Training: 3.2.1. Disaster Recovery Cloud Basics https://youtu.be/iE1sIEydNYE
* DR Basics | Acronis Cyber Disaster Recovery Cloud | Acronis Cyber Cloud Demo Series https://youtu.be/0G_KZgPBlY0
* Disaster Recovery Multi-Site IPsec VPN Configuration | Acronis Cyber Cloud Demo Series https://youtu.be/EWFmswp9QpA
    
![Acronis YouTube Channel](assets/2022-04-03%2016_29_39-Acronis%20-%20YouTube.png "Acronis YouTube Channel")
       
-----------

## Evaluating in Azure
Whilst you can backup and protect Azure IaaS VMs there is no seperate solution or agents to be used from the on-prem solution; there is a single set of install binaries and agents that are the same whether the Windows VM, for example, is running in your own on-premises or in an Azure Datacenter.

**Note** you should however be aware of some of the langauage/ nomenclature used in documentation/UI. This may refer to *on-premises* which in our case would mean *Azure*; a **local** *site* or *network* or *instance* would refer to *Azure*; and a *Physical Machine/ Server* in the UI would be an *Azure VM*. 

Those are just a few examples; in essence you can think of Azure as a remote datacenter of yours, a colocation facility, another site on your WAN/ MPLS for example.

----
## Deployment Workflow

**Install | Configure | Oprerate**

This guide will walk you through deploying a sandboxed infrastructure - the general flow will be as follows:

* **Prerequisites**

* **Part 1 - Deploy Acronis Agent**: In this step, you'll deploy the Acronis Agent; this can be carried out directly from the Azure Portal via a VM extension, or it can be downloaded directly on the VM to be protected by downloading an install file via a browser from the Acronis portal.

* **Part 2 - Configure Acronis Disaster Recovery**: In this step, you'll *configure the protection of the virtual machines*; this will include *creating a recovery plan* as well as *implementing VPN connectivity* between the Azure and Acronis platforms, and finally creating the *recovery server(s)* that you can failover to.

* **Part 3 - Operation of your Acronis DR solution**: With your deployment completed, you're now ready to explore many of the management and operational aspects within the Acronis portal; such as carrting out *failover* and *failback* operations.

---

## Deployment Steps
This *next section* contains the steps you need to start implementing the DR solution.

### Prerequisites

In order to complete the deloyment steps you must have access to the Acronis and Azure Portals as below.

* Access to **Acronis Cyber Cloud Portal** for the company that you wish to protect resources for; the URL for this portal is: https://eu-cloud.acronis.com/
* Access to **Azure Portal** for the tenants subscriptions that you wish to protect resources for; the URL for this portal is: https://portal.azure.com

//Additional content can be aded here...//

--------

### Part 1 - Deploy Acronis Agent

The Acronis agent can be addded by two methods.

1. **Azure Portal using a VM extension**; this is the most streamlined process and has the most integrated feel, from within the VM resource to protect you install the Azure Virtual Machine Acronis Extension and once completed your *Acronis Agent configured Azure VM* will appear in the Acronis Portal under *Machines with agents* screen of the **DEVICES** section on the left hand navigation menu of the portal UI. You can also see the status if the agent from *Agents* screen of the **SETTINGS** section on the left hand navigation menu of the portal UI. *This may take a few minutes to appear*

       //Add Azure Portal Extension Image here...//

       //Add Acronis portal Image here...//

   Information on extensions can be found at this URL:
    * https://docs.microsoft.com/en-us/azure/virtual-machines/extensions/overview

2. **Acronis Portal and download installer**; in this method you are required to login to the VM (*interactively via RDP session*), then from a browser access the *Cyber Protect Portal Console* and download the appropriate agent installer and install directly on the VM to be protected.

       //Add Acronis portal Image here...//

   Information on agent installation can be found at these URLs:
    * https://kb.acronis.com/content/55052
    * Manual install of agent https://youtu.be/ZpR7G0kW-CI
    * Install agent via *VM extension* in *Azure portal* https://youtu.be/ZpR7G0kW-CI
    * Agent-based Backups of Windows Machine | Acronis Cyber Backup Cloud |Acronis Cyber Cloud Demo Series https://youtu.be/BhfZdQI0SDg

   Full and detailed information on Acronis Backup and Recovery can be found at this URL:
    * https://www.acronis.com/en-us/support/documentation/CyberProtectionService/#backup-and-recovery.html

//Additional content can be aded here...//

----

### Part 2 - Configure for Acronis Disaster Recovery (DR)

#### Workflow steps
1. Create **Protection Plan**; should be set to *backup entire machine, or disks*
2. Create at least **1 Recovery Point** before you can perform a failover to a *Recovery Server*
3. Create **VPN Connectivity** between Azure and Acronis; create an **Acronis Multi-Site IPsec VPN** Configuration
4. Create **Recovery Server(s)**


#### Prerequisites
Before you can configure *protection* for your Azure Virtual Machine, you **must have completed** *steps 1* and *2* from the worklow steps in this **Part 2** section of this eval guide *i.e. you must have created a **Protection Plan** and created at least* **1 Recovery Point**.

#### 1. Create Protection Plan & Recovery Point

Now that the *Acronis agent* has been isntalled on the Azure VM to be protected, and shows under *All devices* of the *Devices section* of the *Acronis Cyber Cloud Portal*, you are now ready to create a **Protection Plan**, and at least **1 Recoevry Point**.

       //Add Acronis portal Image here...//

The following URLs provide step by step demos of creating the first *Protection Plan* and *Recovery Point*:
* https://www.youtube.com/watch?v=AcgIMh0qdK8
* https://youtu.be/ZpR7G0kW-CI

//Additional content can be aded here...//

#### 2. Create VPN Connectivity

The following URL provides step by step demos of creating a *Site-to-Site IPsec VPN*:
https://www.youtube.com/watch?v=EWFmswp9QpA&feature=youtu.be

//Additional content can be aded here...//

#### 3. Create Recovery Server(s)

The following URL provides step by step demos of creating a *Recovery Server(s)*:
https://youtu.be/ygFcqnrXrn4

//Additional content can be aded here...//

----

### Part 3 - Operation of your Acronis DR solution

#### Workflow steps
1. Perform *failover* operation
2. Perform *failback* operation

The following URL provides step by step demos of creating a *failover and failback*:
https://youtu.be/ygFcqnrXrn4

----------------
**[Click Here to go Back to Top](#Acronis-Teknov8-AzureDR-EvalGuide-Draft01)**

## Questions / feedback

*Any questions can be addressed to the partner*

//Additional content can be aded here...//

