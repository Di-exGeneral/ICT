# **Module 2: Discover Active Directory**
## **1. The Role of a Directory Service**
- Network directory services store information about a computer network and offer features to retrieve and manage that information. 

- While often viewed as an administrator's tool, users rely on directory services to find network resources. 

- Directory services provide centralized management, but due to their complexity, they require careful planning prior to setup. 
### **Active Directory Domain Services (AD DS) Foundation**
- **AD DS Role:** Provides network directory services based on standards for defining, storing, and accessing directory service objects. 

- **X.500:** Serves as the basis for the hierarchical structure of AD DS. 

- **LDAP (Lightweight Directory Access Protocol):**

  - Based on the X.500 Directory Access Protocol. 

  - Uses the more efficient TCP/IP protocol. 

  - Required when integrating non-Windows operating systems (such as Linux) into an Active Directory network. 

- **Key Features:** Offers hierarchical organization, a centralized/distributed database, scalability, security, flexibility, and policy-based administration. 
## **2. Active Directory Structure: Physical vs. Logical**
Active Directory consists of two distinct structural aspects: 

| **Structural Aspect** | **Description / Components** |
| --- | --- |
| **Physical Structure** | • **Sites:** Physical locations where domain controllers communicate and replicate information periodically. • **Domain Controllers (DCs):** Windows Server 2022 computers running the AD DS role that store domain data, handle search/retrieval, and provide authentication/authorization.  |
| **Logical Structure** | • **Organizational Units (OUs):** Containers used to organize users and resources into logical administrative groups. • **Domains:** Core structural units representing administrative, security, and policy boundaries. • **Trees:** Groupings of domains sharing a common naming structure (parent and child domains). • **Forests:** Collections of one or more trees that share a common environment where all domains can communicate and share information.  |
## **3. Installing Active Directory and Domain Controllers**
- **Prerequisites:** Installed via Server Manager. If DNS is not present on the network, the DNS Server role must also be installed. Post-installation configuration is done by clicking the notification flag and selecting "Promote this server to a DC". 

- **Deployment Options:**

  - Add a domain controller to an existing domain. 

  - Add a new domain to an existing forest (Child domain or new tree). 

  - Add a new forest. 

- **Server Core & PowerShell Installation:**

  - Install role: Install-WindowsFeature AD-Domain-Services -IncludeManagementTools. 

  - Create new forest: Install-ADDSForest -DomainName "csmtech.corp". 

  - Add DC to existing domain: Install-ADDomainController -DomainName "csmtech.corp". 

  - Add child domain: Install-ADDomainController -NewDomainName "europe" -ParentDomainName "csmtech.corp" -DomainType ChildDomain. 

- **Install from Media (IFM):** Reduces replication traffic when building new DCs. Uses the ntdsutil command-line utility to create a snapshot/defragmented database copy (ifm: create full c:\IFMdata). 
## **4. Active Directory Objects and Management Tools**
- **Schema:** Defines the rules of the database. **Schema classes** define object types, **schema attributes** define stored information fields, and **attribute values** are the actual data stored. 
### **Container Objects vs. Leaf Objects**


| **Object Category** | **Sub-types / Examples** | **Description / Default Containers** |
| --- | --- | --- |
| **Container Objects** | • Organizational Units (OUs)• Folder Objects• Domain Objects | • **Builtin:** Houses default Windows groups. • **Computers:** Default location for new computer/server accounts. • **ForeignSecurityPrincipals:** External domain user accounts added to local groups. • **Managed Service Accounts:** Dedicated for services accessing domain resources.• **Users:** Stores default user accounts (Administrator, Guest) and groups.  |
| **Leaf Objects** | • **Security Accounts:** Users, groups, computers. • **Network Resources:** Servers, domain controllers, file shares, printers.  | Objects that do not contain other objects; represent accounts or network resources.  |
- **Active Directory Recycle Bin:** Disabled by default; can be enabled via the Active Directory Administrative Center (ADAC) to restore deleted objects from the *Deleted Objects* container. 

- **Management Tools Comparison:**

  - **Active Directory Users and Computers (ADUC):** Standard MMC snap-in for managing basic domain objects.

  - **Active Directory Administrative Center (ADAC):** Built on PowerShell; executes underlying cmdlets for tasks like creating users, managing OUs, raising functional levels, and enabling the Recycle Bin. 
## **5. Forests, Trees, and Advanced AD Terminology**
- **Replication:** Maintaining database consistency across distributed locations (**Intrasite** within a site, **Intersite** between sites, using **multimaster replication** and the **Knowledge Consistency Checker / KCC**). 

- **Directory Partitions:** Sections of the AD database including Domain, Schema, Global Catalog, Application, and Configuration partitions. 

- **FSMO Roles (Flexible Single Master Operation):** Five operations master roles required in a forest/domain: 

  - Schema Master 

  - Domain Naming Master 

  - RID Master 

  - PDC Emulator Master 

  - Infrastructure Master 

- **Global Catalog (GC):** Facilitates forest-wide searches, cross-domain logins via User Principal Name (UPN), and stores universal group memberships. 

- **Forest Root Domain:** The first domain created; if it fails, the entire structure ceases to operate. 
## **6. Group Policy**
- **Group Policy Object (GPO):** A list of settings used to configure user and computer environments remotely. Managed via the **Group Policy Management Console (GPMC)**. 

- **Default GPOs:** Created automatically when Active Directory is installed: 

  - *Default Domain Policy*

  - *Default Domain Controllers Policy*

- **GPO Configuration Nodes:**

  - **Computer Configuration:** Contains Software Settings, Windows Settings, and Administrative Templates affecting computers in the targeted container. 

  - **User Configuration:** Contains similar subfolders (plus Folder Redirection) affecting domain users within the GPO's scope. 

- **Application Order of Precedence:**

  - Local Computer 

  - Site 

  - Domain 

  - Organizational Unit (OU) 

  - *Rule:* Policies are applied in this sequence, with the **last applied policy taking precedence**.


