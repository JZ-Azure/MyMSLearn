## Azure Virtual Machines (IaaS)
- Virtual machine scale sets: create and manage a group of identical, load-balanced VMs
  - automatically increase or decrease in response to demand
  - or scale based on a defined schedule
  - automatically deploy a load balancer
- Virtual machine availability sets: build a more resilient, highly available environment
  - Update domain: The update domain groups VMs that can be rebooted at the same time.
  - Fault domain: The fault domain groups your VMs by common power source and network switch.

### Create VM
create a Linux VM
```bash
az vm create \
  --resource-group learn-23da9b52-cd51-438c-b7c6-afbf5ef5e4aa \
  --name my-vm \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
```
configure Nginx
```bash
az vm extension set \
  --resource-group learn-23da9b52-cd51-438c-b7c6-afbf5ef5e4aa \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'
```

## Azure Containers
- If you want to run multiple instances of an application on a single host machine, containers are an excellent choice.
- Unlike virtual machines, you don't manage the operating system for a container

### Azure Container Instances (PaaS)
Example
- split a website into a container hosting your front end, another hosting your back end, and a third for storage.

## Azure functions
- Azure Functions is an event-driven, serverless compute option that doesn’t require maintaining virtual machines or containers. 
- Azure Functions runs your code when it's triggered and automatically deallocates resources when the function is finished.
- Functions can be either stateless or stateful. 
  - stateless (the default), they behave as if they're restarted every time they respond to an event. 
  - stateful (called Durable Functions), a context is passed through the function to track prior activity.
- Functions are a key component of serverless computing.

## Virtual Networking
Azure virtual networks and virtual subnets enable Azure resources, such as VMs, web apps, and databases, to communicate with each other, with users on the internet, and with your on-premises client computers.
- Communicate with on-premises resources
  - Point-to-site
  - Site-to-site
  - Azure ExpressRoute
- Connect virtual networks
  - You can link virtual networks together by using virtual network peering.

## Example: Configure network access
Attempt to access VM address
```bash
IPADDRESS="$(az vm list-ip-addresses \
  --resource-group learn-0d90a9e8-c744-4217-a3ce-04947bfb9b41 \
  --name my-vm \
  --query "[].virtualMachine.network.publicIpAddresses[*].ipAddress" \
  --output tsv)"
```
```bash
curl --connect-timeout 5 http://$IPADDRESS
```
```bash
curl: (28) Connection timed out after 5001 milliseconds
```
Check permission
```bash
az network nsg list \
  --resource-group learn-0d90a9e8-c744-4217-a3ce-04947bfb9b41 \
  --query '[].name' \
  --output tsv
```
```bash
az network nsg rule list \
  --resource-group learn-0d90a9e8-c744-4217-a3ce-04947bfb9b41 \
  --nsg-name my-vmNSG \
  --query '[].{Name:name, Priority:priority, Port:destinationPortRange, Access:access}' \
  --output table
```
```bash
Name              Priority    Port    Access
-----------------  ----------  ------  --------
default-allow-ssh  1000        22      Allow
```
Configure access to port 80
```bash
az network nsg rule create \
  --resource-group learn-0d90a9e8-c744-4217-a3ce-04947bfb9b41 \
  --nsg-name my-vmNSG \
  --name allow-http \
  --protocol tcp \
  --priority 100 \
  --destination-port-range 80 \
  --access Allow
```
```bash
az network nsg rule list \
  --resource-group learn-0d90a9e8-c744-4217-a3ce-04947bfb9b41 \
  --nsg-name my-vmNSG \
  --query '[].{Name:name, Priority:priority, Port:destinationPortRange, Access:access}' \
  --output table
```
```bash
Name              Priority    Port    Access
-----------------  ----------  ------  --------
default-allow-ssh  1000        22      Allow
allow-http        100        80      Allow
```
Access again
```bash
curl --connect-timeout 5 http://$IPADDRESS
```
```bash
<html><body><h2>Welcome to Azure! My name is my-vm.</h2></body></html>
```

## Virtual Private Networks
### VPN gateways
A VPN gateway is a type of virtual network gateway.
- You can deploy only one VPN gateway in each virtual network. 
- However, you can use one gateway to connect to multiple locations

Types of connectivity
- Connect on-premises datacenters to virtual networks through a site-to-site connection.
- Connect individual devices to virtual networks through a point-to-site connection.
- Connect virtual networks to other virtual networks through a network-to-network connection.

High-availability scenarios
- Active/standby
- Active/active

## Azure ExpressRoute
Azure ExpressRoute lets you extend your on-premises networks into the Microsoft cloud over a private connection, with the help of a connectivity provider.
- ExpressRoute connections don't go over the public Internet. This allows ExpressRoute connections to offer more reliability, faster speeds, consistent latencies, and higher security than typical connections over the Internet.

## Azure DNS
DNS domains in Azure DNS are hosted on Azure's global network of DNS name servers, providing resiliency and high availability.



