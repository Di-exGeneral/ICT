# **Module 1: Dive Into Windows Server Hybrid Infrastructure**
## **1. The Role of a Server Operating System**
- The specific functions a server performs depend on the following factors: 

  - The type of business using the server. 

  - The size of the business. 

  - The extent to which the business has committed to using technology to aid operations. 

- A server is defined as technology that provides the services a business needs to support its operations. 

- A computer becomes a server when software is installed on it that provides network services to client computers. 
### **Server Operating Systems vs. Desktop Operating Systems**


| **Feature / Attribute** | **Desktop OS (e.g., Windows 11)** | **Server OS (e.g., Windows Server 2022)** |
| --- | --- | --- |
| **Interface & Design** | Features full user interface bells and whistles.  | Deemphasizes UI bells and whistles; **Server Core** (no GUI) is the default installation option.  |
| **Performance Tuning** | Optimized for foreground user applications. | Performance-tuned to run background processes so clients access network services faster.  |
| **Role Support** | Supports only Hyper-V, File and Printer Sharing, Web Server, and FTP Server in limited capacity. | Full support for comprehensive server roles and role services. |
| **User Connection Limits** | Restricted to a maximum of 20 logged-on network users.  | Limited only by the number of purchased licenses.  |
| **Fault-Tolerance Features** | Limited out-of-the-box fault tolerance. | Includes built-in fault tolerance such as **RAID volumes**, **load balancing**, and **clustering**.  |
## **2. Windows Server 2022 Roles, Features, and Common Server Types**
- **Server Role:** A major function or service that a server performs. 

- **Role Services:** Add additional functions to a main role. 

- **Server Features:** Provide functions that enhance/support an installed role or add a stand-alone function. 

- **Installation:** Managed via Server Manager by selecting **Manage** > **Add Roles and Features**. 
### **Common Server Types and Protocols**


| **Server Type** | **Primary Function / Mechanism** |
| --- | --- |
| **Web Server** | Processes HTTP requests from clients and returns HTTP responses over the internet.  |
| **Mail Server** | Relays and routes mail across the internet using **SMTP** (Simple Mail Transfer Protocol).  |
| **DNS Server** | Resolves domain names (e.g., example.com) into corresponding IP addresses (e.g., 100.101.102.103).  |
| **Proxy Server** | Acts as an intermediary behind a firewall to handle client requests to the internet securely.  |
| **FTP Server** | Facilitates file transfers to clients over a LAN or the internet.  |
| **Origin & Edge Servers** | Works via ISPs and content delivery architectures to serve cached and original content.  |
## **3. Windows Server 2022 Core Technologies**
Windows Server 2022 includes ten core technologies: 

1. **Server Manager:** A single interface for installing, configuring, and removing server roles/features, diagnosing problems, managing storage, and viewing dashboard summaries. 

1. **NTFS (New Technology File System):** Allows administrators to set user and group permissions on folders and files to specify access controls and actions, increasing security. 

2. **Microsoft Management Console (MMC):** Creates a centralized management interface using **snap-ins** (such as Disk Management) to perform specific administrative tasks, including remote management from a Windows 11 workstation. 

1. **Disk Management:** Used to monitor disk/volume status, initialize new disks, create/format volumes, troubleshoot disk issues, and configure RAID. 

1. **File and Printer Sharing:** Provides advanced storage and sharing capabilities such as shadow copies, disk quotas, and the Distributed File System (DFS). 

1. **Windows Networking Concepts & Components:**

  1. **Networking Models:** Operates via a **Windows workgroup** (peer-to-peer / standalone server) or a **Windows domain** governed by a **domain controller** running AD DS. 

  1. **Network Connections:** Composed of a network interface (NIC and driver) and network protocols (**TCP/IPv4** and **TCP/IPv6**). 

  1. **Client vs. Server Software:** *Client for Microsoft Networks* sends requests to access resources, whereas *File and Printer Sharing for Microsoft Networks* receives requests and shares resources. 

1. **Active Directory Domain Services (AD DS):** Turns a server into a domain controller, handling authentication and authorization while providing a centralized database for deploying policies, installing software, and applying patches. 

1. **PowerShell:** An interactive command-line scripting environment utilizing **verb-noun pairs** (cmdlets), parameters, variables, pipelines (|), and command filtering (Get-Command). 

1. **Hyper-V and Cloud Computing:**

   1. Uses virtualization and hypervisors to run multiple virtual machines (VMs) and guest OSs on a physical host computer. 

  1. Categorizes cloud services into **public clouds** (third-party like OneDrive) and **private clouds** (internal IT services accessed via VDI). 

1. **Storage Spaces:** Utilizes virtual drives to build scalable storage pools from mixed drive types (USB, SATA, SAS) and non-standard disk sizes with support for **thin provisioning**. 
## **4. Windows Server Hybrid Infrastructure and Microsoft Azure**
- **Hybrid Infrastructure Definition:** The combination of Windows Server running on-premises and Windows Server running in the Microsoft Azure cloud. 

- **Cloud Attributes:** Scalable, Agile, and Current. 
### **Cloud Service Models Comparison**


| **Cloud Model** | **Description / Core Focus** | **Examples / Context** |
| --- | --- | --- |
| **SaaS (Software as a Service)** | Customers pay for the use of applications running on a service provider's network.  | Dropbox, OneDrive, Google Apps.  |
| **PaaS (Platform as a Service)** | Customers develop applications using the service provider's tools and infrastructure.  | Developer environments and app hosting platforms. |
| **IaaS (Infrastructure as a Service)** | Companies use a provider's computing power, storage, and infrastructure services as needed.  | **The core focus of Microsoft Azure**.  |
### **Working with Azure Virtual Machines**
- **Quickstart Center:** The starting hub in Azure used to deploy web apps, create VMs, and set up databases. 

- **Azure VM Access:**

  - New Azure VMs running Windows Server 2022 have **Remote Desktop Protocol (RDP)** enabled by default over a public IP address for initial UI configuration. 

  - Best practice recommends **disabling RDP** after the initial setup phase is complete. 

  - Connection is established by selecting the VM name, clicking **Connect**, choosing **RDP**, downloading the .rdp file, and logging into the desktop environment.


