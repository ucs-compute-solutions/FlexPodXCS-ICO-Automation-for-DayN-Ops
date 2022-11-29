# FlexPodXCS-ICO-Automation-for-DayN-Ops

This repo contains FlexPodXCS day-1/2 operations workflow automation using Intersight Cloud Orchestrator. Few critical work-flows identified as first set of FlexPodXCS day-1/2 operations. This list of operations contains most frequently used administrative and configuration tasks needed for their existing FlexPod environment. These tasks include essential operations on compute, network, storage and virtualization components that are part of a Flex Pod converged infrastructure solution.

Here is the sample list of operations that are planned for automation through ICO workflows -

<img width="928" alt="Screenshot 2022-10-28 at 1 26 02 PM" src="https://user-images.githubusercontent.com/12057795/198726221-79bf8e7a-4435-4aad-9e6e-2090f8283773.png">


As mentioned before these automation workflows can be executed against an existing running and Cisco Validated Design(CVD) compliant FlexPod environment that has been claimed into an Intersight account with administrative priveleges. Target for these workflow execution is a FlexPodXCS instance as created on Intersight. In order to have an existing FlexPod environment claimed into intersight following pre-requisites are expected to be in place - 

1.

<img width="1155" alt="Screenshot 2022-10-28 at 1 06 03 PM" src="https://user-images.githubusercontent.com/12057795/198722933-fdce0cc7-f165-41dd-bfd9-a6645ff65741.png">

2. For example only -

<img width="1121" alt="Screenshot 2022-10-28 at 1 06 28 PM" src="https://user-images.githubusercontent.com/12057795/198722992-b2821836-48d1-4b24-9fec-3564605831fa.png">

3. This represents actual physical topology for a typical iSCSI protocol based FlexPod environment -

![NexusSAN-Topology](https://user-images.githubusercontent.com/12057795/202779485-71a31898-26a6-4514-af2d-38d6f935d193.jpg)

4.

<img width="1095" alt="Screenshot 2022-10-28 at 1 07 27 PM" src="https://user-images.githubusercontent.com/12057795/198723122-fb0e6ab5-3c13-431a-a5a3-e6997b0dac09.png">

Following references can help in setting up FlexPod XCS environment -
  - FlexPod Datacenter with Cisco UCS 4.2(1) in UCS Managed Mode, VMware vSphere 7.0 U2, and NetApp ONTAP 9.9 - https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/flexpod_m6_esxi7u2.html
  - FlexPod Datacenter with End-to-End 100G, Cisco Intersight Managed Mode, VMware 7U3, and NetApp ONTAP 9.11 Design Guide - https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/flexpod_ucs_xseries_e2e_ontap_design.html
  - FlexPod XCS: The First Cisco Intersight Integrated System - https://www.cisco.com/c/en/us/solutions/collateral/data-center-virtualization/flexpod/flexpod-xcs-solution-intersight.html
