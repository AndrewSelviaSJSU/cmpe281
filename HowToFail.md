# How To Fail

1. NAT Gateway allows instances in a private subnet to reach out to the internet. An internet gateway (igw) controls which external IPs are able to reach instances in a public subnet. I had put the NAT Gateway on my Public Subnet. This prevented me from being able to ssh into my jumpbox. The solution was to return the public subnet to use the igw so that external hosts could reach it. The NAT gateway was really only needed to allow the mysqldb instance to download mysql onto itself since it lives in the private subnet.

2. default VPC

    Resolution:
    1. https://us-west-2.console.aws.amazon.com/vpc/home?region=us-west-2#vpcs
    2. Select *default*
    3. Select *Actions*
    4. Select *Delete VPC*

3. Didn't remember to register instances in target group as indicated in the *Create Target Groups* section of Lab 2 AWS.md. This resulted in the target groups lacking targets and the message: "There are no targets registered to this target group".

4. When I added the new loadtest1.php & loadtest2.php files to the aws-php image at `/var/www/html`, I thought they would somehow get propagated to the AMI and all new instances would have them. That was wrong. The instances that got created by the php-launch-config had the old fibonacci.php files, but not the new ones. I realized then that new files did not automatically get added to an AMI. I needed to first add them to an instance, then stop it, and create a new AMI from it. I looked for a way to update the existing AMI, but I did not find any way to do that. Any time you update an AMI, I currently believe you must also create a new launch configuration; though, assuming you make a similar mistake on a future lab quiz, note that it seems you can copy an existing launch config by selecting the existing launch config, then selecting the *Copy launch configuration* button it its *Details* pane. From there, you can simply change the AMI it uses. Then, you must propagate the change to the Auto Scaling groups you created from that launch configuration. To do that, you must select the respective Auto Scaling groups, select the *Actions* button, select *Edit*, and change the *Launch Configuration* to the new one using the new AMI.

5. Creating Auto Scale Groups without ELB Target Group; In his instructions, the professor said to create *Auto Scale Group #1*. One of the fields specified was ELB target group. It wasn't immediately obvious where to input that value, though. I skipped it. The effect of this decision became clear once I ran loadtest1.php. When the first instance surpassed its CPU Utilization threshold, the Auto Scale group did spin up a second instance. However, since the ELB was not hooked up, traffic did not go to the new instance. If you attempted to reach loadtest1.php, it would continue going to the first instance rather than cycling round-robin to the new one.

    Resolution:
    1. Select the desired Auto Scaling group
    2. Select *Actions*
    3. Select *Edit*
    4. Select *Target Groups*
    5. Select the desired target group (*php-target-1* and *php-target-2*, respectively, for Lab Quiz 1)
    6. Select *Save*
    
6. How to convert a bunch of PDF Screen Shots into a single PDF for upload to Canvas?
```
convert *.png ScreenShots.pdf
```
