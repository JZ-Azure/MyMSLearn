- physical organization of Azure
  - datacenters
  - availability zones
  - regions
- organizational structure of Azure
  - resources
  - resource groups
  - subscriptions
  - management groups

## Physical infrastructure
- Region: a geographical area on the planet that contains at least one, but potentially multiple datacenters that are nearby and networked together with a low-latency network.
  - Some services or VM features are only available in certain regions.
  - Some global Azure services don't require a region, such as Azure Active Directory, Azure Traffic Manager, and Azure DNS.
- Availability Zones: physically separate datacenters within an Azure region.
  - Each availability zone is made up of one or more datacenters equipped with independent power, cooling, and networking
  - An availability zone is set up to be an isolation boundary. If one zone goes down, the other continues working. 
  - Availability zones are connected through high-speed, private fiber-optic networks.
  - To ensure resiliency, a minimum of **three** separate availability zones are present in all availability zone-enabled regions. 
  - Not all Azure Regions currently support availability zones.
 - Region pairs: Most Azure regions are paired with another region within the same geography (such as US, Europe, or Asia) at least 300 miles away.
 - Sovereign Regions: Sovereign regions are instances of Azure that are isolated from the main instance of Azure.
  - You may need to use a sovereign region for compliance or legal purposes.
  - US DoD Central, US Gov Virginia, US Gov Iowa and more
  - China East, China North, and more

## Azure management infrastructure
- Resource group
  - a single resource can only be in one resource group at a time
  - resource groups can't be nested
- Subscriptions: unit of management, billing, and scale
  - You can use Azure subscriptions to define boundaries around Azure products, services, and resources.
    - Billing boundary
    - Access control boundary
  - Create additional Azure subscriptions
    - Environments
    - Organizational structures
    - Billing
- Management groups: Azure management groups provide a level of scope above subscriptions
  - All subscriptions within a management group automatically inherit the conditions applied to the management group
  - Management groups can be nested
  - Create one Azure role-based access control (Azure RBAC) assignment on the management group, for all sub-management groups, subscriptions etc



