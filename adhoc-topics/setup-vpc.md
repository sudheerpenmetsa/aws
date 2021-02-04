# Networking
## Create VPC
Step 1: Search for VPC and go to create VPC
Step 2: Add details
   - Name : 
   - CIDR block : 10.0.0.0/26
   - Click "create vpc"
   - Calculate CIDR block
     10.0.0.0/26
     Start - 10.0.0.0
     2 ^ (32-26) = 2 ^ 6 = 64
     End - 10.0.0.63 

## Create Subnet
- Step 1: Click subnet from left side menu
- Step 2: Click "create subnet" button
- Step 3: Select VPC from drop down
Step 4: Subnet Settings
    - subnet name : sudheer-private-2a
    - availability zone : 
    - CIDR block : 10.0.0.0/28
    - Click "create subnet"
- Step 5: click "Add new subnet" 
    - subnet name : sudheer-private-2b
    - availability zone : 
    - CIDR block : 10.0.0.16/28
    - Click "create subnet"
    - click "create subnet"

- if you want to create two more subnets
CIDR blocks will be 10.0.0.32/28 and 10.0.0.48/28
```
** Available Ip's for each subnet are showing as 11, although we assigned 16. Its because, when ever a subnet is created 5 IPs are reserved for internal usage and not available to us.
what are those 5 IP addresses, every subnet of first 4 IPs and last one IP address.
```

## Route Tables:

```
*** We have one route table available with our VPC.
*** Any VPC created, one route will be created and it is called as "main" table.
*** Will create two route tables, one for private subnet and other one for public
```
- Step 1: Rename the main route table.
- Step 2: Create new route table
       - Name tage : name for toute table
       - VPC : select VPC from drop down menu
       - Click "create"
```
Now these route tables are not associated with any subnet by explicitly, that means "main" route table of the VPC will be used for **All** the subnet.
```
- Step 3 : Associate route table to subnets
   - select the "private route table"
   - Click "subnet associations" tab below
   - Click "edit subnet associations"
   - Select the private subnet and save
   - select the "public route table" 
   - Click "subnet associations" tab below
   - Click "edit subnet associations"
   - Select the public subnet and save
```
** One subnet can have only one route table
** One route table can be associated to multiple subnets 
```
```
** Now there is no difference in both the route tables. Now we need to make the changes, so that  one will made as public and other will be private.
** when subnet considered as public?
when there is a route available in the assocaiated route table to the internet gateway. Internet gateway is an entity which allows connectivity from our VPC to outside world
```
### Create internet gateway
- Create internet gateway and atatch it to a VPC
```
** You can see only one VPC is displaying because only one Internet Gateway can be attached to a VPC, we cannot attach "n" number of gateways to VPC
```
### Edit Public Route tables:
- Public route table
    - Select public route table
    - select "routes" tab from below
    - Click "edit"
    - click "add route"
    - Now we will send all the internet bound traffic from this particular subnet(0.0.0.0/0) . Select "Internet Gateway from "target" tab and select the IG created"

## NAT Gateway (Managed service)
What is the importance of NAT Gateway?
NAT Gateway helps all the internet bound traffic which is getting originated from private Instances to go to internet and it gets reply from internet and sends to private instances.

- Step 1 : Select NAT Gateway from left side menu
- Step 2:
   - Name:
   - subnet: Always we need to keep the NAT Gateway in public subnet

### Edit Private route tables
- Select route table from left side menu
- Select private route table
- select "routes" from below tabs
- Click "edit" and add route
- Anything bound to internet traffic send to NAT Gateway

## Modify auto-assign IP settings.
- we need to modify  "auto-assign public IP " settings to true for public subnet. This property will shown when you are launching  instances in this particular subnet.
When instances are launched in public subnet they should get a public IP, so we are enabling this option.

## Modify VPC to enable DNS hostnames
- select VPC and click actions
- select edit DNS hostnames and enable and save
- Select edit DNS resolution and enable and save

## Elastic IP 
Elastic IP address is a public static IPv4 address which is reachable from the Internet. Basically Elastic IP addresses are used by AWS to manage its dynamic cloud computing services. Within the AWS infrastructure, customers have virtual private clouds (VPC), within the VPCs, users have instances. So when you launch an EC2 instance, you receive a Public IP address by which that instance is reachable from internet. Once you stop that instance and restart the instance you get a new Public IP for the same instance. So it's basically a problem to connect your instance from internet for not having a static IP. To overcome this problem, we attach an Elastic IP to an Instance which doesn't change after you stop / start the instance.

In short Elastic IP is a permanent IP for your instance.


## Public IP :
A Public IP address is how the internet identifies you. A public IP address is the IP address that communicates your internet connected device to the public internet

REF : https://medium.com/@datapath_io/elastic-ip-static-ip-public-ip-whats-the-difference-8e36ac92b8e7