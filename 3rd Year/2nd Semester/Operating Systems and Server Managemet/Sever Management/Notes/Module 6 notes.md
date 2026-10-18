# **Module 6: Manage Windows Server in a Hybrid Environment**
## **1. Working with Server Roles and Features**
- **Overview:** Windows Server requires roles and features to be added to unlock full functionality beyond basic file and printer sharing. These can be managed via GUI tools or Server Core installations. 

- **Management Tools:**

  - **Server Manager GUI:** Accessed via the **Add Roles and Features Wizard** (or removed via *Remove Roles and Features*). 

  - **PowerShell Cmdlets:**

- Get-WindowsFeature: Lists available and installed roles and features

- Install-WindowsFeature: Installs a specified server role or feature. 
## **2. Managing Servers Remotely**
- **Benefits:** Remote management allows administrators to utilize Server Core while operating a GUI from a remote machine, reducing physical hardware requirements.

- **Server Manager Grouping:** Large organizations can organize servers into groups (by department, location, or function) which can be added via Active Directory, DNS, or a text file import. 

- **PowerShell Remoting & Second-Hop:**

  - Use the -ComputerName parameter to run remote commands. 

  - Configured via Enable-PSRemoting, Disable-PSRemoting, and Test-WSMan. 

  - **Second-hop remoting** (accessing a third server from a remote session) is supported using CredSSP, Kerberos delegation, or **Just Enough Administration (JEA)**. 

- **Just Enough Administration (JEA):** Limits delegated administrative tasks to specific cmdlets, functions, and external commands using role capability files and registered JEA endpoints. 

- **Windows Firewall Rules:** Remote management via MMCs requires specific inbound rule groups to be enabled, such as *COM+ Network Access* and *Remote Event Log Management* (via netsh or Set-NetFirewallRule). 
## **3. Deploying Windows Admin Center**
- **Definition:** A browser-based management tool for on-premises and Azure VM servers. 

- **Deployment Options:**
### **Windows Admin Center Installation Scenarios**


| **Installation Type** | **Description & Use Case** |
| --- | --- |
| **Local Client** | Installed locally to manage remote or local environments.  |
| **Gateway Server** | Installed on a Windows Server (default port 443 with HTTPS and self-signed certificate) allowing any enterprise client to manage servers via web browser.  |
| **Managed Server** | Installed directly on a server so it can be managed from a client browser.  |
| **Failover Cluster** | Installed as a gateway across a cluster for high availability.  |
## **4. Managing Windows Servers with Azure Services**
- **Azure Arc:** A platform that bridges on-premises servers and other public clouds into Azure management tools using the **Connected Machine agent**. 

- **Capabilities via Arc:**

  - **Azure Policy Guest Configuration:** Enforces configuration compliance. 

  - **Insights & Monitoring:** Integrates Log Analytics, Update Management, Inventory, and Change Tracking. 

- **Microsoft Defender for Cloud & JIT Access:**

  - Centralizes security configuration and reporting for hybrid environments. 

  - **Just-in-Time (JIT) VM Access:** Permits administrators to access a VM only by request for a specified duration, requiring an associated Network Security Group (NSG). 

- **Runbooks:** Sets of procedures utilizing PowerShell, PowerShell Workflow, or Python within an Automation account to automate repetitive tasks. 

## **5. Managing Servers with Desired State Configuration (DSC)**
- **Definition:** A feature enabling management and maintenance of servers using simple declarative statements. 

- **Operating Modes:**

  - **Push Mode:** Configurations are manually sent to target servers by an administrator. 

  - **Pull Mode:** Target servers automatically pull their configurations from a central server using standard web protocols. 

- **Azure Automation DSC:** Prevents configuration drift on Azure VMs by uploading configuration files, compiling them, registering the VM, and assigning node configurations.


