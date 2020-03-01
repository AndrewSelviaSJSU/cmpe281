# AWS Reference Guide

## [VPC and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
* If a subnet's traffic is routed to an internet gateway, the subnet is known as a **public subnet**. In this diagram, subnet 1 is a public subnet.
* If a subnet doesn't have a route to the internet gateway, the subnet is known as a **private subnet**. In this diagram, subnet 2 is a private subnet.
* There is no option for a subnet to be inherently private or public; this characteristic is determined by the **routing table** the subnet is attached to.
* [Link to subnets diagram](https://docs.aws.amazon.com/vpc/latest/userguide/images/subnets-diagram.png)

## [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html), [NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html), and [Gateway Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)
* Internet Gateways allow connections to be established **both** from within the associated subnet(s) **and** outside from the internet.
* NAT Gateways allow connections to be established **only** from within the associated subnet(s).
* **NOTE:** Traffic from already established connections can still flow in either direction. See below.

## [Inbound and Outbound Rules](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)
* _Inbound_ Security Group rules refer to the address space, ports, and protocols that **connections** can be established from.
* _Outbound_ Security Group rules refer to the address space, ports, and protocols that **traffic** can flow to.

## [Internet-Facing Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internet-facing-load-balancers.html) and [Internal-Facing Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internal-load-balancers.html) 

## Tips and Tricks
* Convert .jpg to .pdf
   * _Print to PDF_ --- Windows & Mac
   * ImageMagick convert --- Mac & Ubuntu
   * Ampare PDF ---- img to pdf w/ gui --- Ubuntu
```
convert *.png ScreenShots.pdf
```
