---
title: Installing Redis for Pivotal Cloud Foundry&reg;
owner: London Services
---

<a id="install"></a>
## Installation Steps

To add Redis for PCF to Ops Manager, follow the procedure for adding Pivotal Ops Manager tiles:

1. Download the product file from [Pivotal Network](https://network.pivotal.io/products/p-redis).
1. Upload the product file to your Ops Manager installation.
1. Click **Add** next to the uploaded product description in the Available Products view to add this product to your staging area.
1. (Optional) Click the newly added tile to configure your [possible service plans](#configure) and [syslog draining](#syslog).
1. Click **Apply Changes** to install the service.

<a id="configure"></a>
## Configuring Redis Service Plans

Select the **Redis** tile from the Installation Dashboard to display the configuration page and configure the Redis service plans.

### Shared-VM Plan

1.  Select the **Shared-VM Plan** tab to configure the memory limit for each Redis instance and the maximum number of instances that can be created.

    <br />The memory limit of your Redis instances should depend on the capacity and RAM of your Redis Broker and the number of instances that will be used. By default, the number of instances and memory limit of each instance could lead to 2.5GB of your Redis Broker being used to run your Shared-VM Redis instances.

1.  Select the **Resource Config** tab to change the allocation of resources for the Redis Broker.

    <br />The Redis Broker server will run all of the Redis instances for your Shared-VM plan. From this screen you may increase or decrease the CPU, RAM, Ephemeral Disk & Persistent Disk made available, as required.

1.  Click the **Save** button.

### Dedicated-VM Plan

1.  Select the **Resource Config** tab to change the allocation of resources for the Dedicated Node.

    <br />By default, 5 dedicated nodes will be created, each capable of running one Redis instance. You can increase or decrease the number of dedicated nodes, the size of the Persistent and Ephemeral Disks, and the CPU and RAM, as required.

1.  Click the **Save** button.


<a id="syslog"></a>
## Configuring Syslog Output

1.  Select the **Syslog** tab.
1.  Add the **syslog destination address**, **port** and **protocol** (TCP/UDP/RELP). The information required for these fields will be provided by your log management tool.

    <br />The default syslog protocol for fresh deployments is TCP. If you are upgrading from Redis for PCF v1.5 and already have the syslog drain configured, the syslog drain will continue to use UDP as before.

1.  Click the **Save** button.
