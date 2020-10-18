## Building Amazon Virtual Private Cloud (VPC) with AWS CloudFormation

In this task, I create a Amazon Virtual Private Cloud (VPC) with AWS CloudFormation

### The process of this project

1)`VPC` Network Structure

![VPC Network Structure](image/Network-Structure.png)

![VPC](image/VPC.png)

2)`Internet Gateway` is the scaled and highly available `VPC` components that allows the communication between instances in the `VPC` and the outside internet.

ii) It provide a target in the `VPC` route tables for Internet-routable traffic

iii) It performs the `network address translation (NAT)` for instances that have been assigned with  public IPv4 addresses.

![Internet Gateway](image/InternetGateway.png)

3)Types of `VPC` Subnet 

i) `Public subnet` is connected to Internet via Internet Gateway and can be used by resources that are needed to be publicly accessible.

ii) `Private subnet` cannot be connected to Internet and can be used by resources that are needed to be privately accessible.

![Subnet](image/Subnet.png)

4) `Route Tables` are used to direct the traffic in and out of subnets. The configuration for the route table is 

    - For traffic within the VPC (10.0.0.0/16), route the traffic locally

    - For trafic going to the Internet (0.0.0.0/0), route the traffic to the Internet Gateway

![RouteTable](image/RouteTable.png)













