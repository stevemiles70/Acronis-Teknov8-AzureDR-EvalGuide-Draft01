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

* **Part 2 - Configure Acronis Agent**: In this step, you'll configure the protection of the VMs; this will include creating a recovery plan as well as implementing connectivity between the Azure and Acronis platforms.

* **Part 3 - Explore the management and operation of your Acronis DR solution**: With your deployment completed, you're now ready to explore many of the management and operational aspects within the Acronis portal.

---

## Deployment Steps
This *next section* contains the steps you need to start implementing the DR solution.

*First thing though, this will require you to have the following things in place first:*

### Prerequisites

//Content to be aded here...//

--------

### Part 1 - Deploy Acronis Agent

//Content to be aded here...//


### Part 2 - Configure Acronis Agent

//Content to be aded here...//


### Part 3 - Explore the management and operation of your Acronis DR solution

//Content to be aded here...//

----------------

\
\
**[Click Here to go Back to Top](#Acronis-Teknov8-AzureDR-EvalGuide-Draft01)**

## Questions / feedback

*Any questions can be addressed to the partner*

