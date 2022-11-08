# ICO workflow to provision new storage to hypervisor cluster in FlexPodXCS environment

This workflow helps in provision a new NFS Datastore on FlexPodXCS instance. It takes care of 2 use-cases - 1. Provisioning and mounting datastore on existing hypervisor cluster on an existing SVM and 2. Provision a new SVM, NFS LIFs and volume on storage backend then mount the datastore on existing hypervisor cluster. User can decide between these 2 options during workflow execution as a workflow input. In order to use this workflow, an account administrator in Intersight need to import included json file into Orchestration feature. Once imported successfully, one can execute it against a FlexPodXCS instance needing new storage provisioning and making it available via NFS protocol to hypervisor cluster. 


Workflow is consisting of 3 sub-workflows and corresponding tasks to perform actions on NetApp storage backend and hypervisor cluster managed by VMWare vCenter. Following operations gets executed in sequential order as part of workflow execustion - 

When New SVM needed -
1. A new storage virtual machine gets created on NetApp ONTAP cluster having an HA-pair of 2 controllers
2. New logical interfaces(lif) gets created on each controller of a HA-pair cluster(sub-workflow consisting of 2 task one each for 2 controllers)
3. A new NetApp SMART volume gets created with user defince performance service level, enablement of local snapshot copies, volume capacity & name along with access permission details
4. Export policy addition to new smart volume
5. Export policy rule addition
6. Creation of a new NFS datastore on hypervisor cluster using smart volume created at the NetApp storage backend in previous steps

When an existing SVM is used -
1. A new NetApp SMART volume gets created with user defined performance service level, enablement of local snapshot copies, volume capacity & name along with access permission details
2. Export policy addition to new smart volume
3. Creation of a new NFS datastore on hypervisor cluster using smart volume created at the NetApp storage backend in previous steps

*** **Please note - Workflow execution must be done on the same intersight org where the FlexPod XCS instance was created and is planned to operate on. Currently account administrator privilege is required.** ***

Parent workflow looks like below when imported successfully - 

<img width="758" alt="Screenshot 2022-11-02 at 8 07 53 PM" src="https://user-images.githubusercontent.com/12057795/199640532-74d87f42-1956-4e07-9aec-0359528dcada.png">

Corresponding sub-workflows are -
1. New SVM use case 

<img width="605" alt="Screenshot 2022-11-02 at 8 08 53 PM" src="https://user-images.githubusercontent.com/12057795/199640652-eb90a7de-a799-4e69-ac69-29648a2794f8.png">

2. Existing SVM use case

<img width="539" alt="Screenshot 2022-11-02 at 8 09 46 PM" src="https://user-images.githubusercontent.com/12057795/199640736-252e020a-ad4f-428f-ba7b-5192158e2952.png">

A successful execution will look like as below -

<img width="1567" alt="Screenshot 2022-11-02 at 8 11 09 PM" src="https://user-images.githubusercontent.com/12057795/199640866-37e29521-06b6-44a8-9ef1-52d70536eb2d.png">

