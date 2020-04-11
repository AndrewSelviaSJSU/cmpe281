# AWS Reference Guide

## [VPC and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)
* If a subnet is associated with a routing table that has an internet gateway, that subnet is known as a **public subnet**. In the linked diagram, subnet 1 is a public subnet.
* If the subnet's routing table does **not** have an internet gateway, the subnet is known as a **private subnet**. In the linked diagram, subnet 2 is a private subnet.
* There is no option that makes a subnet inherently private or public; this characteristic is determined by the **routing table** the subnet is associated with.
* [Link to subnets diagram](https://docs.aws.amazon.com/vpc/latest/userguide/images/subnets-diagram.png)

## [Internet Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html), [NAT Gateways](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html), and [Gateway Route Tables](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)
* Internet Gateways allow **connections** to be established both from **within** and **outside** of the associated subnet(s).
* NAT Gateways allow connections to be established only from **within** the associated subnet(s).
* **NOTE:** Traffic from established connections can still flow in either direction.

## [Inbound and Outbound Rules](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)
* _Inbound_ Security Group rules refer to the address space, ports, and protocols that **connections** can be established from.
* _Outbound_ Security Group rules refer to the address space, ports, and protocols that **traffic** can flow through.

## [Internet-Facing Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internet-facing-load-balancers.html) and [Internal-Facing Load Balancers](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internal-load-balancers.html) 

## Tips and Tricks
* Convert multiple .png to .pdf
   * _Print to PDF_ --- Windows & Mac
   * ImageMagick convert --- Mac & Ubuntu
   * Ampare PDF ---- img to pdf w/ gui --- Ubuntu
```
convert *.png ScreenShots.pdf
```
