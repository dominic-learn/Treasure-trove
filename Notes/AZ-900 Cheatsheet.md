# AZ-900: Azure Fundamentals — Cheat Sheet

## Cloud Concepts

**Service Models**
| Model | You Manage | Provider Manages | Example |
|---|---|---|---|
| IaaS | OS, apps, data, runtime | Virtualization, servers, storage, network | Azure VMs |
| PaaS | Apps, data | + OS, runtime | App Service |
| SaaS | Data/config only | Everything else | Microsoft 365 |

**Deployment Models**
- **Public** – hosted by Azure, shared infra
- **Private** – dedicated, on-prem or hosted
- **Hybrid** – mix of public + private

**Benefits**: High availability, scalability (vertical/horizontal), elasticity, agility, fault tolerance, disaster recovery, CapEx→OpEx shift, consumption-based pricing, global reach.

**Economies of scale**: Larger scale = lower per-unit cost.

---

## Core Architectural Components

- **Region** – geographic area with datacenters
- **Region Pair** – two regions in same geography (recovery)
- **Availability Zone (AZ)** – physically separate datacenters within a region (min 3 per enabled region)
- **Availability Set** – logical grouping (Fault Domains + Update Domains) within one datacenter
- **Resource** – single manageable item (VM, DB, etc.)
- **Resource Group** – container for related resources
- **Subscription** – billing + access boundary
- **Management Group** – organizes multiple subscriptions

**Hierarchy**: Management Groups → Subscriptions → Resource Groups → Resources

**Sovereign/Government clouds**: Azure China, Azure Government (isolated instances).

---

## Compute Services

| Service | Use Case |
|---|---|
| Virtual Machines | Full control IaaS |
| VM Scale Sets | Auto-scaling identical VMs |
| App Service | Host web apps (PaaS) |
| Azure Functions | Serverless, event-driven, pay-per-execution |
| Container Instances (ACI) | Single container, fast spin-up |
| AKS | Managed Kubernetes |
| Azure Batch | Large-scale parallel/batch jobs |

---

## Networking

- **Virtual Network (VNet)** – private network in Azure
- **Subnet** – segment of a VNet
- **VPN Gateway** – encrypted connection over public internet
- **ExpressRoute** – private, dedicated connection to Azure (not over internet)
- **Load Balancer** – Layer 4, distributes traffic
- **Application Gateway** – Layer 7, web traffic, SSL termination, WAF
- **VNet Peering** – connect VNets, private IP traffic
- **DNS** – name resolution
- **NSG (Network Security Group)** – filter traffic to/from resources
- **Azure Firewall** – managed, stateful network firewall
- **CDN** – caches content close to users

---

## Storage

| Type | Purpose |
|---|---|
| Blob | Unstructured object storage (hot/cool/archive tiers) |
| Disk | VM disks (managed) |
| File | SMB/NFS file shares |
| Queue | Message storage between apps |
| Table | NoSQL key-value store |

**Redundancy**:
- **LRS** – 3 copies, 1 datacenter
- **ZRS** – copies across AZs, 1 region
- **GRS** – LRS + async copy to paired region
- **GZRS** – ZRS + async copy to paired region
- **RA-GRS/RA-GZRS** – read access to secondary region

**Migration tools**: Azure Migrate, Data Box (offline, physical), Storage Explorer, AzCopy.

---

## Identity, Access & Security

- **Azure AD (Entra ID)** – cloud identity service (authentication)
- **RBAC** – Role-Based Access Control (authorization; assigned at scope: MG/Sub/RG/Resource)
- **MFA** – Multi-Factor Authentication
- **Conditional Access** – policies based on conditions (location, device)
- **SSO** – Single Sign-On
- **Zero Trust** – "never trust, always verify"
- **Defender for Cloud** – Cloud Security Posture Mgmt (CSPM) + workload protection
- **Azure Sentinel** – SIEM/SOAR (cloud-native security analytics)
- **Key Vault** – store secrets, keys, certificates
- **Shared Responsibility Model** – security split shifts: you manage more in IaaS, less in SaaS

---

## Governance & Compliance

- **Azure Policy** – enforce rules/effects on resources (e.g., "deny", "audit")
- **Blueprints** – package policies + role assignments + templates for repeatable deployment
- **Resource Locks** – `CanNotDelete` / `ReadOnly`
- **Tags** – metadata key-value pairs for organizing/billing
- **Compliance Manager / Trust Center** – compliance documentation
- **Service Trust Portal** – audit reports, compliance guides

---

## Cost Management

- **Pricing Calculator** – estimate costs before deployment
- **TCO Calculator** – compare on-prem vs Azure cost
- **Azure Cost Management** – monitor/analyze spend
- **Factors affecting cost**: resource type, region, bandwidth (egress costs, ingress free), subscription type

---

## Management & Governance Tools

- **Azure Portal** – GUI
- **Azure CLI / PowerShell** – command-line
- **Azure Cloud Shell** – browser-based CLI
- **Azure Resource Manager (ARM)** – deployment/management layer; ARM templates = JSON IaC
- **Azure Arc** – manage on-prem/multi-cloud resources via Azure
- **Azure Monitor** – collect/analyze telemetry
- **Service Health** – status of Azure services affecting you
- **Azure Advisor** – personalized best-practice recommendations

---

## SLA / Uptime

- Azure SLA guarantees uptime %; **Composite SLA** = combined SLA of chained services (multiplies).
- Common tiers: 99.9% / 99.95% / 99.99%

---

## Quick Definitions

- **IaC** – Infrastructure as Code (ARM templates, Bicep, Terraform)
- **FinOps** – cloud financial management practice
- **DevOps** – Azure DevOps / GitHub Actions for CI/CD
- **Serverless** – no server management, auto-scale, consumption billing
