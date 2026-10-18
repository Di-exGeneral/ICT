# **Module 4: Configure Group Policies**
## **1. Group Policy Objects and Architecture**
- **GPO Components:** Group policies involve GPOs (objects containing configuration and security settings), replication across domain controllers, creation/linking via management tools, and scope defining affected users and computers. 

- **Types of GPOs:** GPOs are categorized into **Local GPOs** and **Domain GPOs**. 
### **Local vs. Domain Group Policy Objects**


| **GPO Type** | **Storage Location & Management** | **Key Characteristics** |
| --- | --- | --- |
| **Local GPOs** | Stored locally on individual computers; edited via the Group Policy Object Editor (gpedit.msc).  | • Settings inherited from domain GPOs cannot be overwritten locally.• Only undefined or unconfigured domain settings can be edited locally. • Contains *Computer Configuration* and *User Configuration* nodes.  |
| **Domain GPOs** | Stored in Active Directory on domain controllers; managed using the **Group Policy Management Console (GPMC)**.  | • Consists of two separate parts: **Group Policy Templates (GPT)** and **Group Policy Containers (GPC)**. • Changes take effect immediately upon client download without requiring a manual save option.  |
- **GPT vs. GPC Structure:**

  - **Group Policy Template (GPT):** Located in the SYSVOL share on domain controllers. Contains actual policy settings and related files like scripts. Every GPT folder contains at least GPT.ini, Machine, and User. 

  - **Group Policy Container (GPC):** Stored in Active Directory. Stores GPO properties and status information, but **no policy settings**. 

- **GPO Replication:** GPCs replicate via Active Directory. GPTs in the SYSVOL share replicate using either **File Replication Service (FRS)** (for mixed server environments) or **Distributed File System Replication (DFSR)** (recommended for Windows Server 2008 and later). 

- **Starter GPOs:** Act as templates (not GPTs) for creating new GPOs and can be saved as CAB files. 

## **2. Configuring Group Policy Settings**
- **Conflict Resolution:** Settings configured under **Computer Configuration** take precedence over settings under **User Configuration**. 

- **Managed vs. Unmanaged Policies:**

  - *Managed policies* automatically reset to 'Not configured' when the object moves outside the policy's scope. 

  - *Unmanaged policies* are persistent. 

### **Software Installation, Scripts, and Folder Redirection**


| **Feature / Policy Extension** | **Description & Configuration Options** |
| --- | --- |
| **Software Installation** | • Uses the Windows Installer service and **Microsoft Software Installation (.msi)** files. • **Computers:** Packages are *assigned* to target computers and installed during startup from a shared folder granting Read & execute permissions. • **Users:** Packages can be *published* (available manually via Programs and Features) or *assigned* (installed automatically upon logon).  |
| **Deploying Scripts** | • Series of commands saved in batch files (.bat). • Configured as *startup/shutdown scripts* under Computer Configuration or *logon/logoff scripts* under User Configuration.  |
| **Folder Redirection** | • Redirects folders in a user's profile directory to network shares. • Applies strictly to user accounts under the **User Configuration** node. • Supports redirecting **13 specific folders** (such as Documents, Pictures, Desktop, and Downloads).  |
## **3. Administrative Templates**
- **Definition:** Administrative templates are XML-formatted text files (.admx) that define settings in the Administrative Templates folder. Language-specific user interface files use the .adml extension. 

- **ADMX Central Store:** A centralized location on domain controllers for maintaining ADMX files so updates propagate automatically to all DCs. 

- **Filtering:** Policies can be filtered in the Group Policy Management Editor (GPME) using criteria such as Managed, Configured, Commented, Keyword filters, and Requirements filters. 

- **Migrating Legacy Templates:** Older template files (.adm used prior to Windows Vista/Server 2008) can be converted to the modern .admx format using the **ADMX Migrator** tool. 

## **4. Group Policy Preferences**
- **Purpose:** Preferences establish a baseline computing environment while allowing users to modify configured settings locally. 

- **Structure:** Available under both Computer Configuration and User Configuration nodes within **Windows Settings** and **Control Panel Settings**. Requires the Group Policy Preferences Client Side Extensions (GPP CSE) package. 

- **Refresh Schedule:** Refreshed by default every 90 minutes (plus computer startup or user logon). Unlike managed policies, preference settings are **not** automatically restored to their original state when removed. 

- **Item-Level Targeting:** Allows administrators to apply preferences dynamically only if specific criteria are met (e.g., operating system version, hardware attributes like a battery presence). 
## **5. Group Policy Processing and Inheritance**
### **GPO Scope, Precedence, and Inheritance Rules**
- **Processing Order:** Applied sequentially from broadest to most specific:

  - Local policies 

  - Site-linked GPOs 

  - Domain-linked GPOs 

  - OU-linked GPOs 

  - *Note:* The **last policy applied takes precedence** in a conflict. Fine-tuning should occur at the OU level. 

- **Inheritance Controls:**

  - **Blocking Inheritance:** Prevents GPOs linked to parent containers from affecting child containers. 

  - **GPO Enforcement:** Forces inheritance of settings on all child objects, overriding conflicting settings deeper in the hierarchy. Enforced GPOs hold the strongest precedence. 

### **GPO Filtering and Loopback Processing**
- **Security Filtering:** Uses access control permissions to restrict or grant access to a GPO for specific security principals. 

- **WMI Filtering:** Uses Windows Management Instrumentation queries (e.g., selecting Windows 10 Enterprise via Select * from Win32_OperatingSystem where Caption = "Microsoft Windows 10 Enterprise") to conditionally apply policies based on hardware or OS attributes. 

- **Loopback Policy Processing:** Applies user configuration settings based on the computer object's container scope rather than the user's container scope (commonly used in shared environments like conference rooms). 

## **6. Implementing Group Policy in Azure AD DS**
- **Management:** Group Policy in Azure AD DS is managed similarly to on-premises AD using an Azure VM joined to the Azure AD DS domain. 

- **Default AADDS GPOs:** Azure AD DS initializes with two default GPOs: 

  - **AADDC Computers GPO**

  - **AADDC Users GPO**


