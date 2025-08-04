# SampleTechSpire
This project demonstrates secure VNet-to-VNet connectivity in Microsoft Azure using VNet Peering and implements custom RBAC to enforce least privilege access.

# 🌐 Enterprise-Grade Azure VNet Integration with Custom Roles

## 📘 Project Title  
**Secure Azure Networking with VNet Peering and Custom RBAC**

---

## 📝 Description  
This project was implemented for Techspire’s client to simulate a real-world enterprise scenario where the organization is evaluating Microsoft Azure as a deployment platform. It focuses on establishing secure network connectivity and enforcing least privilege access using custom role-based access control.

## 🎯 Project Objectives

- Deploy internet-facing workloads across isolated virtual networks  
- Establish secure communication between networks using **VNet Peering**  
- Onboard a user into **Azure Active Directory (Azure AD)**  
- Create and assign a **Custom Role-Based Access Control (RBAC)** role adhering to the **Principle of Least Privilege**

---

## 🔐 RBAC Scope of Access

The onboarded user is granted the following permissions:

- View resources such as **Virtual Machines**, **Virtual Networks**, and **Storage Accounts**  
- Start and restart **Virtual Machines**  
- Access is restricted to only the resources defined within the custom RBAC role


---

## 📌 Tasks Performed

### 🔧 Network & VM Setup
- Created two Virtual Networks:
  - `Techspirevnet01` (10.0.0.0/16) with `Techspiresubnet01` (10.0.0.0/24)
  - `Techspirevnet02` (10.1.0.0/16) with `Techspiresubnet02` (10.1.0.0/24)
- Deployed test VMs:
  - `TechspireVM01` in `Techspirevnet01`
  - `TechspireVM02` in `Techspirevnet02`
- Configured **VNet Peering** between `Techspirevnet01` and `Techspirevnet02`

## 📡 Connectivity Testing

- Enabled **ICMP (Ping)** using PowerShell on both virtual machines  
- Verified **cross-VM communication** through **RDP access** and **ping tests**


### 👥 User & Custom RBAC Role
- Onboarded a new user in Azure AD
- Created a custom RBAC role: `ComputerOperator`
- Assigned the following permissions:
  - `Microsoft.Compute/virtualMachines/read`
  - `Microsoft.Compute/virtualMachines/start/action`
  - `Microsoft.Compute/virtualMachines/restart/action`
  - `Microsoft.Network/virtualNetworks/read`
  - `Microsoft.Storage/storageAccounts/read`
  - `Microsoft.Storage/storageAccounts/blobServices/containers/read`
  - `Microsoft.Resources/subscriptions/resourceGroups/read`
  - `Microsoft.Resources/subscriptions/read`
- Assigned the role to the user
- Verified permissions by logging in as the user and successfully restarting a VM

---

## 🏁 Project Outcomes

- ✅ Successfully implemented secure **VNet Peering** between isolated virtual networks  
- ✅ Verified end-to-end **VM-to-VM connectivity** across peered networks  
- ✅ Applied a **custom RBAC role** to enforce precise access control  
- ✅ Effectively demonstrated the **Principle of Least Privilege** in a real-world scenario

---

## 🧰 Tools & Technologies Utilized

- **Microsoft Azure Portal**  
- **Azure Active Directory (Azure AD)**  
- **Azure Virtual Networks (VNets)** and **Virtual Machines (VMs)**  
- **Azure Role-Based Access Control (RBAC)**  
- **PowerShell** – for configuring network and firewall settings  
- **Remote Desktop Protocol (RDP)** – for virtual machine access and testing

---


## 📸 Screenshots

Refer to the `/screenshots` directory for visual documentation of the following:

- Configuration of **Virtual Networks** and **Subnets**  
- Setup of **VNet Peering** between isolated networks  
- Creation and assignment of a **Custom RBAC Role**  
- **User onboarding** process and access validation

---


## 👨‍💻 Author  
**Shubham Tripathi**

---
