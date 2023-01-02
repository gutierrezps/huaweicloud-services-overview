# Huawei Cloud services overview

<!-- markdownlint-disable-next-line no-inline-html -->
<a href="https://www.huaweicloud.com/intl/en-us/"><img width="450px" height="102px" src="https://console-static.huaweicloud.com/static/authui/20210202115135/public/custom/images/logo-en.svg"></a>

This project aims to be like a cheatsheet for Huawei Cloud by listing common
services, a brief description of them and links to their respective Help Center
page.

## Useful links

- [Cloud Console][console]
- [Help Center][help-center] - services documentation, tutorials ("Getting
  Started" tab) and FAQs ("Self Service" tab)
- [Worldwide Infrastructure][worldwide-infra] - check which services are
  available in each Region
- [Price Calculator][calculator]
- [Public Cloud Services Comparison][cloud-compare] - see how Huawei Cloud
  services are named on other cloud providers

For developers:

- [Huawei Cloud API Explorer][api-explorer]
- [Terraform HuaweiCloud Provider][terraform-provider]

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

[Pricing][pricing]: resources on Huawei Cloud are billed by different
modes. The most common ones are: yearly/monthly, where you choose the period
specified and you are charged in advance (prepaid); and pay-per-use, a postpaid
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
BMSs are deployed in multiple AZs, and work with VPC, EIP, IMS, EVS, VBS,
Cloud Eye and CBR services.

[IMS: Image Management Service][ims] allows you to manage the entire lifecycle
of your images. An image is a cloud server or disk template that contains an
operating system (OS), service data, or necessary software. You can create ECSs
or BMSs from public, private, or shared images. You can also create a private
image from a cloud server or an external image file.

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

[FunctionGraph][functiongraph] is the serverless computing service of Huawei
Cloud. It hosts and computes event-driven functions in a serverless context
while ensuring high availability, high scalability, and zero maintenance.
Write/upload your code in Node.js, Python, Java, Go, C#, or PHP; set execution
conditions; and pay only for what you use (you are not charged when it's not
running).

[DeH: Dedicated Host][deh], a physical server that runs only ECSs from your
account. Bring Your Own License (BYOL). Traditional ECSs, in contrast, run in
a server together with ECSs from other accounts/tenants.

[DeC: Dedicated Cloud][dec], a complete resource isolation solution by using
dedicated services, such as Dedicated Distributed Storage Service (DSS),
Dedicated Enterprise Storage Service (DESS), and Bare Metal Server (BMS). DeH,
in contrast, can provide only isolated compute hosts.

[HPC: High-Performance Computing][hpc], a computer cluster system that connects
multiple computer systems using various interconnection technologies. It relies
on the integrated computing capability of all the connected systems to perform
large-scale computing tasks.

## Storage

### Types

[EVS: Elastic Volume Service][evs] is the block storage of Huawei Cloud. EVS
disks are similar to hard disks in PCs. They must be attached to servers for
use and cannot be used alone. You can initialize EVS disks, create file systems
on them, and store data persistently on them. Cloud servers that EVS supports
include ECSs and BMSs. EVS disks are sometimes just referred to as disks.

[SFS: Scalable File Service][sfs] provides scalable, high-performance file
storage (Network Attached Storage, NAS). With SFS, you can enjoy shared file
access spanning multiple ECSs, BMSs and containers created on CCE. SFS supports
Network File System (NFS, for Linux) and Common Internet File System (CIFS, for
Windows) protocols.

[OBS: Object Storage Service][obs] is a scalable service that provides secure,
reliable, and cost-effective cloud storage for massive amounts of data. OBS
basically consists of buckets - a container for storing objects in OBS; and
objects - the fundamental storage unit in OBS. There is no limitation on the
storage capacity of the entire OBS system or of a single bucket, and any number
of objects can be stored. There are three storage classes available: Standard,
for frequently accessed files; Infrequent Access, for files accessed less than
12 times per year; and Archive, for data accessed once a year.

### Backup and DR

[CBR: Cloud Backup and Recovery][cbr] enables you to back up ECSs, BMSs, EVS
disks, SFS Turbo file systems, local files and directories, and on-premises
VMware virtual environments with ease. CBR consists of: backups, the copies of
particular chunks of data; vaults, where the generated backups are stored; and
policies, which can be for backup or for replication, and set execution times,
frequency and retention rules. CBR integrates Cloud Server Backup Service
(CSBR) and Volume Backup Service (VBS), which were separate services in the
past.

[SDRS: Storage Disaster Recovery Service][sdrs] provides cloud disaster
recovery (DR) for your data centers. If your on-premises or cloud data center
fails, you can fail over services to the DR center on Huawei Cloud, and then
fail back the services after the production center recovers.

### Others

[CDN: Content Delivery Network][cdn] is a smart virtual network on the Internet
infrastructure. CDN can cache origin content on nodes closer to users, so
content can load faster. CDN speeds up site response and improves site
availability.

[DES: Data Express Service][des] is a TB-scale data transmission service. It
provides physical storage devices (such as Teleport, external USB hard disks,
SATA disks, and SAS disks) to make it easier for you to transmit terabytes of
data to HUAWEI CLOUD.

[DSS: Dedicated Distributed Storage Service][dss] provides you with dedicated
storage pools which are physically isolated from other pools to ensure high
security. By flexibly interconnecting with various compute services, such as
Dedicated Computing Cluster (DCC), ECS and BMS, DSS is suitable for different
scenarios, including HPC, online analytical processing (OLAP), and mixed loads.

## Networking

[VPC: Virtual Private Cloud][vpc] enables you to provision logically isolated
virtual private networks for cloud resources, such cloud servers, containers,
and databases. You can create custom subnets, security groups, network ACLs,
and assign EIPs and bandwidths. By default, ECSs in all subnets of the same VPC
can communicate with one another, but ECSs in different VPCs cannot.

- [Subnet][subnet] is a unique CIDR block with a range of IP addresses in a
  VPC. All resources in a VPC must be deployed on subnets. When you create a
  VPC, a default subnet will be created together.

- [Security Group][secgroup] is a collection of access control rules for cloud
  resources that have the same security protection requirements and that are
  mutually trusted. Those rules will apply to all cloud resources added to the
  security group. Rules can be for inbound traffic (into the protected
  services) or outbound traffic (originated from the protected services), and
  can allow or deny such traffic based on source/destination, protocol and
  port.

- [Network ACL][netw-acl] is an optional layer of security for your subnets.
  After you associate one or more subnets with a network ACL, you can control
  traffic in and out of the subnets.

[EIP: Elastic IP][eip] is a public IP address that can be accessed directly
over the Internet. An EIP consists of a public IP address and some amount of
public network egress bandwidth. EIPs can be bound to or unbound from ECSs,
BMSs, virtual IP addresses, NAT gateways, and load balancers.

[ELB: Elastic Load Balance][elb] automatically distributes incoming traffic
across multiple backend servers based on the listening rules you configure,
eliminating single points of failure. ELB = (Listener) + (Backend server
group).

- [Listener][elb-listener] uses the protocol and port you specify to check for
  requests from clients and route the requests to associated backend servers
  based on the listening rules and forwarding policies you configure. Supports
  Layer 4 (TCP and UDP) and Layer 7 (HTTP and HTTPS) protocols.

- [Backend server group][elb-backend] contains one or more backend servers to
  receive requests routed by the listener. You need to add at least one backend
  server to a backend server group. You can set a weight for each server in the
  backend server group. The larger the weight is, the higher proportion of
  requests the backend server receives. Backend servers can be dynamically
  added/removed through an Auto Scaling setup.

[NAT Gateway][natgw] is a network address translation (NAT) service. It can be
a public NAT gateway or a private NAT gateway. A public NAT gateway uses an
EIP to enable cloud and on-premises servers in a private subnet to access the
Internet (source NAT, SNAT), or to make services in a VPC accessible from the
Internet (destination NAT, DNAT). Private NAT gateways allows ECSs and BMSs in
a VPC to communicate with servers in other VPCs or on-premises data centers,
translating the source and destination IP addresses of originating packets into
a transit IP address.

[VPN: Virtual Private Network][vpn] establishes an encrypted, Internet-based
communication tunnel between your on-premises data center and a VPC, so that
you can access service resources in the VPC from your on-premises data center.
Currently, only IPsec VPN is supported, in a site-to-site scheme.

[DNS: Domain Name Service][dns] is a highly available and scalable
authoritative DNS service that translates domain names (such as
`www.example.com`) into IP addresses (such as `192.1.2.3`) required for network
connection. The DNS service allows users to visit your websites or web
applications with domain names.

[Direct Connect][dc] allows you to establish a stable, high-speed, low-latency,
secure dedicated network connection that connects your on-premises data center
to Huawei Cloud. Direct Connect allows you to maximize legacy IT facilities and
leverage cloud services to build a flexible, scalable hybrid cloud computing
environment.

[VPCEP: VPC Endpoint][vpcep] is a cloud service that provides secure and
private channels to connect your VPCs to VPC endpoint services, including cloud
services or your private services. It allows you to plan networks flexibly
without having to use EIPs. There are two types of resources: VPC endpoint
services, which are cloud services or private services that you manually
configure in VPCEP; and VPC endpoints, which are secure and private channels
for connecting VPCs to VPC endpoint services.

[CC: Cloud Connect][cc] allows you to connect VPCs in different regions to
allow instances in these VPCs to communicate over a private network as if they
were within the same network. You need to load network instances from these
regions to a cloud connection and assign bandwidth for cross-region
communications. (A network instance can be a VPC you create, a VPC of another
user, or a virtual gateway you create for access from your on-premises data
center.)

<!-- Introduction -->
[console]: <https://console-intl.huaweicloud.com/console/?locale=en-us>
[help-center]: <https://support.huaweicloud.com/intl/en-us/index.html>
[worldwide-infra]: <https://www.huaweicloud.com/intl/en-us/global/>
[calculator]: <https://www.huaweicloud.com/intl/en-us/pricing/index.html>
[cloud-compare]: <https://comparecloud.in/>
[api-explorer]: <https://apiexplorer.developer.intl.huaweicloud.com/apiexplorer/doc>
[terraform-provider]: <https://github.com/huaweicloud/terraform-provider-huaweicloud>

<!-- General Concepts -->
[region-az]: <https://support.huaweicloud.com/intl/en-us/usermanual-iaas/en-us_topic_0184026189.html>
[pricing]: <https://www.huaweicloud.com/intl/en-us/product/price.html>
[ecs-billing]: <https://support.huaweicloud.com/intl/en-us/productdesc-ecs/ecs_01_0065.html>

<!-- Computing -->
[ecs]: <https://support.huaweicloud.com/intl/en-us/ecs/index.html>
[ecs-flavor]: <https://support.huaweicloud.com/intl/en-us/productdesc-ecs/en-us_topic_0035470096.html>
[bms]: <https://support.huaweicloud.com/intl/en-us/bms/index.html>
[ims]: <https://support.huaweicloud.com/intl/en-us/ims/index.html>
[as]: <https://support.huaweicloud.com/intl/en-us/as/index.html>
[as-config]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_0042018362.html>
[as-group]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_0042018368.html>
[as-policy]: <https://support.huaweicloud.com/intl/en-us/usermanual-as/en-us_topic_2019013003.html>
[functiongraph]: <https://support.huaweicloud.com/intl/en-us/functiongraph/index.html>
[deh]: <https://support.huaweicloud.com/intl/en-us/deh/index.html>
[dec]: <https://support.huaweicloud.com/intl/en-us/deh_faq/deh_faq_0007.html>
[hpc]: <https://support.huaweicloud.com/intl/en-us/usermanual-hpc/hpc_01_0002.html>

<!-- Storage -->
[evs]: <https://support.huaweicloud.com/intl/en-us/evs/index.html>
[sfs]: <https://support.huaweicloud.com/intl/en-us/sfs/index.html>
[obs]: <https://support.huaweicloud.com/intl/en-us/obs/index.html>
[cbr]: <https://support.huaweicloud.com/intl/en-us/cbr/index.html>
[sdrs]: <https://support.huaweicloud.com/intl/en-us/sdrs/index.html>
[cdn]: <https://support.huaweicloud.com/intl/en-us/cdn/index.html>
[des]: <https://support.huaweicloud.com/intl/en-us/des/index.html>
[dss]: <https://support.huaweicloud.com/intl/en-us/dss/index.html>

<!-- Networking -->
[vpc]: <https://support.huaweicloud.com/intl/en-us/vpc/index.html>
[subnet]: <https://support.huaweicloud.com/intl/en-us/usermanual-vpc/vpc_0001.html>
[secgroup]: <https://support.huaweicloud.com/intl/en-us/usermanual-vpc/en-us_topic_0073379079.html>
[netw-acl]: <https://support.huaweicloud.com/intl/en-us/usermanual-vpc/acl_0001.html>
[eip]: <https://support.huaweicloud.com/intl/en-us/eip/index.html>
[elb]: <https://support.huaweicloud.com/intl/en-us/elb/index.html>
[elb-listener]: <https://support.huaweicloud.com/intl/en-us/usermanual-elb/elb_ug_jt_0001.html>
[elb-backend]: <https://support.huaweicloud.com/intl/en-us/usermanual-elb/elb_ug_hd_0001.html>
[natgw]: <https://support.huaweicloud.com/intl/en-us/natgateway/index.html>
[vpn]: <https://support.huaweicloud.com/intl/en-us/vpn/index.html>
[dns]: <https://support.huaweicloud.com/intl/en-us/dns/index.html>
[dc]: <https://support.huaweicloud.com/intl/en-us/dc/index.html>
[vpcep]: <https://support.huaweicloud.com/intl/en-us/vpcep/index.html>
[cc]: <https://support.huaweicloud.com/intl/en-us/cc/index.html>
