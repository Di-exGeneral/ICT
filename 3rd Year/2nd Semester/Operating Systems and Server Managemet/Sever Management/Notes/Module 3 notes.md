# **Module 3: Manage Active Directory Accounts**
## **1. Working with Organizational Units (OUs) and Permissions**
- **Benefits of OUs:**

  - Creating familiar hierarchical structures based on organizational charts to allow easy resource access. 

  - Delegating administrative authority. 

  - Changing the OU structure easily. 

  - Grouping users and computers to assign administrative and security policies. 

  - Hiding AD objects for confidentiality or security reasons. 

- **Delegation of Control:** A user with higher security privileges assigns authority to someone with lesser security privileges to perform tasks (e.g., creating/deleting/managing user accounts, resetting passwords, and managing groups). 

- **Object Security Descriptor Components:**

  - Discretionary access control list (DACL). 

  - Object owner. 

  - System access control list (SACL). 

- **Permission Inheritance:** Permissions applied to a parent OU using the Delegation of Control Wizard are inherited by all child objects by default.

 

- **Advanced Features Option:** Enabling "Advanced Features" in the View menu of AD Users and Computers reveals five additional system folders: 

  - LostAndFound

  - Program Data

  - System

  - NTDS Quotas

  - TPM (Trusted Platform Module) Devices

## **2. Managing User Accounts**
- **Core Functions:** Provide user authentication to the network and detailed information about a user. 

- **Domain vs. Local Accounts:** Non-domain Windows machines store accounts locally in the Security Accounts Manager (SAM) database, whereas AD domain user accounts can typically log on to any computer within the AD forest. 

- **Creation Rules:** Account names must be unique throughout the domain, are case-insensitive (1 to 20 characters), require complex passwords by default, and require only a logon name initially. 

- **Disabling Accounts:** Accounts may be disabled when users leave the company, take extended leave, or when accounts are not yet ready for use. Supported via ADUC, ADAC, PowerShell (Enable-ADAccount / Disable-ADAccount), or dsmod user. 

### **Summary of User Account Property Tabs**


| **Property Tab** | **Purpose / Function** |
| --- | --- |
| **Account Tab** | Contains settings affecting domain logons (e.g., user logon names, logon hours, logon workstations, account options like password rules, and account expiration dates).  |
| **Profile Tab** | Specifies the path to a user profile, logon scripts, and home folder paths.  |
| **Member Of Tab** | Lists the security and distribution groups to which the user belongs.  |
- **Contacts & Distribution Groups:** A *contact* is an informational object usually representing a person (often for Microsoft Exchange address books), while a *distribution group* is used with Exchange to send emails to multiple people at once. 
## **3. Managing Group Accounts**
- **Purpose:** Group objects serve as the primary security principal used to assign rights and permissions efficiently. 
### **Group Types and Scopes**


| **Group Property** | **Options / Sub-types** | **Description / Characteristics** |
| --- | --- | --- |
| **Group Types** | • **Security Groups**• **Distribution Groups** | • **Security Groups:** Main objects used to grant rights and control network resource access. • **Distribution Groups:** Used exclusively with email applications like Microsoft Exchange to broadcast messages.  |
| **Group Scopes** | • **Domain Local**• **Global**• **Universal**• **Local (SAM)** | • **Domain Local:** Recommended for assigning permissions to local domain resources. • **Global:** Groups users from the same domain with similar access needs (e.g., department or location).• **Universal:** Can contain users and be assigned permissions across any domain in the forest; supports universal group membership caching. • **Local:** Created in the local SAM database of a stand-alone or member workstation/server.  |
- **Group Nesting:** Making a group a member of another group (e.g., nesting global groups) is typically used to group users with similar roles across different departments. 

## **4. Working with Computer and Service Accounts**
- **Computer Accounts:** Created automatically when a client computer joins a domain, granting benefits such as single sign-on, AD searching, group policies, and remote management. Can be created manually in ADUC or via PowerShell (Add-Computer -DomainName DomainName -Restart). 

- **Service Accounts:** Used by background Windows services to log on with specific rights and permissions. 
### **Built-in Service Accounts**


| **Built-in Account** | **Privilege Level / Intended Use** |
| --- | --- |
| **Local Service** | Intended for services and background applications needing minimal rights and privileges.  |
| **Network Service** | Intended for services that require both local and network access.  |
| **Local System** | Has extensive privileges exceeding even the Administrator account; should be used with extreme caution.  |
- **Managed Service Accounts (MSA & gMSA):**

  - **MSA:** Tied to a single specific server, features automatic password management and SPN support, but cannot be locked out or used interactively. 

  - **gMSA (Group MSA):** Provides the same features as an MSA but can be managed and used across multiple servers running Windows Server 2012 or later. 

- **Virtual Accounts:** The simplest service accounts to use because they require zero creation, deletion, or management (e.g., NT Service\EFS). 

- **Kerberos Delegation:** Allows a service to "impersonate a client" to authenticate to another service on the client's behalf using domain accounts assigned a Service Principal Name (SPN). 

## **5. Active Directory in a Hybrid Environment (Azure AD)**
- **Azure AD (AAD):** A multitenant cloud service used primarily to authenticate users accessing Azure cloud resources via common internet security protocols. Accounts use a default domain ending in onmicrosoft.com, though custom domain names can be added. 

- **Azure AD Connect:** An on-premises tool used to synchronize Windows AD users, groups, and contacts with Azure AD. Supports features like password hash synchronization, password writeback, and health monitoring via Azure AD Connect Health. 

- **Azure AD Connect Cloud Sync:** A newer offering where configuration and provisioning information is managed directly in the cloud, supporting disconnected forests with lower on-premises resource utilization. 

- **Azure AD Domain Services (AADDS):** Implements traditional on-premises AD features (such as domain join, Group Policy, LDAP, and Kerberos/NTLM authentication) in the cloud with automated backups, managed patching, and high availability.


