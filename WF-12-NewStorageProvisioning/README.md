# ICO workflow to provision new storage to hypervisor cluster in FlexPodXCS environment

This workflow helps in provision a new NFS Datastore on FlexPodXCS instance - Begin with new SVM and end with hypervisor cluster mounting. In order to use this workflow, an account administrator in Intersight need to import included json file into Orchestration feature. Once imported successfully, one can execute it against a FlexPodXCS instance needing new storage provisioning and making it available via NFS protocol to hypervisor cluster. 

*** **Please note - Workflow import must be done to the same intersight org where the FlexPod XCS instance is being used as target and currently account administrator privileges required to do so.** ***

Workflow is consisting of a sub-workflow and 5 tasks to perform actions on NetApp storage backend and hypervisor cluster managed by VMWare vCenter. Following operations gets executed in sequential order as part of workflow execustion - 

1. A new storage virtual machine gets created on NetApp ONTAP cluster having an HA-pair of 2 controllers
2. New logical interfaces(lif) gets created on each controller of a HA-pair cluster(sub-workflow consisting of 2 task one each for 2 controllers)
3. A new NetApp SMART volume gets created with user defince performance service level, enablement of local snapshot copies, volume capacity & name along with access permission details
4. Export policy addition to new smart volume
5. Export policy rule addition
6. Creation of a new NFS datastore on hypervisor cluster using smart volume created at the NetApp storage backend in previous steps

A typical workflow looks like below when imported successfully - 

<img width="641" alt="Screenshot 2022-10-28 at 1 58 57 PM" src="https://user-images.githubusercontent.com/12057795/198731304-63860209-2564-4f4f-badc-fa1ee821d757.png">


A successful execution will look like as below -

<img width="1616" alt="Screenshot 2022-10-28 at 2 00 30 PM" src="https://user-images.githubusercontent.com/12057795/198731530-9f85c521-7073-490d-9681-ea6d1a8640f9.png">
