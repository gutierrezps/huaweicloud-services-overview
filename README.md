# Huawei Cloud services overview

This project aims to be like a cheatsheet of Huawei Cloud by listing common
services, a brief description of them and links to their respective Help Center
page.

## General concepts

[AZ: Availability Zone][region-az] contains one or more physical data centers.
Each AZ has independent cooling, fire extinguishing, moisture-proof, and
electricity facilities. Within an AZ, computing, network, storage, and other
resources are logically divided into multiple clusters. AZs within a region are
interconnected using high-speed optical fibers to support cross-AZ
high-availability systems.

[Region][region-az] is a group of AZs based on geographical location and
network latency. Public services such as ECS, EVS, OBS, VPC, EIP and IMS are
shared within the same region.

Billing mode: resources on Huawei Cloud can be billed by different
modes. The most common ones are: yearly/monthly, where you choose the period
specified and you are charged in advance (prepaid); pay-per-use, a postpaid
mode where you are billed by a rate that can be based by time (e.g. hourly
rate) or resource usage (e.g. traffic, data volume, number of calls). There are
some free services as well, and also services that have a free tier/quota.
Some service's final price can be composed of other resource's pricing as well.
See [ECS billing][ecs-billing] for example.

## Computing

[ECS: Elastic Cloud Server][ecs], a virtual machine on the Huawei Cloud. Basic
computing unit that consists of vCPUs, memory, OS, and Elastic Volume Service
(EVS) disks.

- [ECS Flavor][ecs-flavor]: name given to the ECS specifications. Combination
of number of vCPUs, vCPU frequency, memory and Network QoS. Flavors are named
in the `AB.C.D` format, where `A` is the type, `B` is the type ID, `C` is the
number of vCPUs and `D` is the vCPU:memory ratio. Type can be: `t` for general
computing basic; `s` for general computing; `c` for general computing plus;
`m` for memory-optimized; `d` for disk-intensive; `i` for ultra-high I/O; `h`
for high-performance; `g` for GPU graphics accelerated; `p` for GPU computing
accelerated; `k`, Kunpeng architecture.

[BMS: Bare Metal Server][bms], a physical server integrated to Huawei Cloud. It
provides dedicated servers on the cloud, delivering performance and security.

[DeH: Dedicated Host][deh], a physical server that runs only ECSs from your
account. Bring Your Own License (BYOL). Traditional ECSs, in contrast, run in
a server together with ECSs from other accounts/tenants.

[DeC: Dedicated Cloud][dec], a complete resource isolation solution by using
dedicated services, such as Dedicated Distributed Storage Service (DSS),
Dedicated Enterprise Storage Service (DESS), and Bare Metal Server (BMS). DeH
can provide only isolated compute hosts.

[AS: Auto Scaling][as], a service that automatically adjusts resources based on
your service requirements and configured AS policies. You can specify AS
policies based on service requirements. AS can automatically adjust ECS and
bandwidth resources. AS = (AS configuration) + (AS group) + (AS policies).

- [AS configuration][as-config] defines the specifications of the ECS instances
to be added to an AS group. The specifications include the ECS image and system
disk size.

- [AS group][as-group] is a collection of instances and AS policies that have
similar attributes and apply to the same application scenario.

- [AS policy][as-policy] defines the conditions for triggering a scaling action
and the operation that will be performed. When the triggering condition is met,
a scaling action is triggered automatically. Conditions can be alarm (according
to a metric value), scheduled (at a specified date and time) or periodic (at a
configured interval, e.g. dayly, weekly, etc).

[HPC: High-Performance Computing][hpc], a computer cluster system that connects
multiple computer systems using various interconnection technologies. It relies
on the integrated computing capability of all the connected systems to perform
large-scale computing tasks.

[region-az]: <https://support.huaweicloud.com/intl/en-us/usermanual-iaas/en-us_topic_0184026189.html>
[ecs-billing]: <https://support.huaweicloud.com/intl/en-us/productdesc-ecs/ecs_01_0065.html>
[ecs]: <https://support.huaweicloud.com/intl/en-us/ecs/index.html>
[ecs-flavor]: <https://support.huaweicloud.com/intl/en-us/productdesc-ecs/en-us_topic_0035470096.html>
[bms]: <https://support.huaweicloud.com/intl/en-us/bms/index.html>
[deh]: <https://support.huaweicloud.com/intl/en-us/deh/index.html>
[dec]: <https://support.huaweicloud.com/intl/en-us/deh_faq/deh_faq_0007.html>
[as]: <https://support.huaweicloud.com/intl/en-us/as/index.html>
[as-config]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_0042018362.html>
[as-group]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_0042018368.html>
[as-policy]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_2019013003.html>
[hpc]: <https://support.huaweicloud.com/intl/en-us/usermanual-hpc/hpc_01_0002.html>