# **Module 7: Configure DNS**
## **1. Structure of DNS and Query Processing**
- **Namespace Structure:** DNS uses an inverted tree structure representing Fully Qualified Domain Names (FQDNs), with root servers managing Top-Level Domain (TLD) servers. 

- **Query Types:**

  - **Iterative Query:** A DNS server responds with the best information it has or provides a referral response. 

  - **Recursive Query:** A DNS server processes the query completely until it provides a matching address or an "I don't know" message. 

- **DNS Server Roles:** A DNS server can function as an *authoritative server*, *forwarder*, *conditional forwarder*, or *caching-only server*. 

## **2. Configuring DNS Zones**
- **Zone Categories & Types:**
### **DNS Zone Types and Categories**


| **Zone Category / Type** | **Description & Characteristics** |
| --- | --- |
| **Forward Lookup Zone (FLZ)** | Translates names to IP addresses; contains records like A, AAAA, and MX.  |
| **Reverse Lookup Zone (RLZ)** | Maps IP addresses to names using PTR records; named after the network address.  |
| **Primary Zone** | Contains a read/write master copy of all resource records and is authoritative for the zone.  |
| **Secondary Zone** | Contains a read-only copy of zone records and is authoritative; requires zone transfers from the primary zone. |
| **Stub Zone** | Contains only SOA, NS, and necessary glue A records; not authoritative.  |
- **Replication Scope & Dynamic Updates:** AD-integrated zones replicate across specific directory partition scopes (such as forest, domain, or custom scopes) and can support secure dynamic updates. 

## **3. Creating DNS Resource Records**
- **Common Resource Records:**
### **Summary of DNS Resource Records**


| **Record Type** | **Description & Function** |
| --- | --- |
| **Host (A / AAAA) Records** | Maps a hostname to an IPv4 (A) or IPv6 (AAAA) address.  |
| **Canonical Name (CNAME)** | Acts as an alias for another domain name record.  |
| **Pointer (PTR) Records** | Resolves an IP address to a hostname; stored in RLZs.  |
| **Mail Exchanger (MX)** | Specifies mail servers responsible for a domain.  |
| **Service Location (SRV)** | Specifies hostnames and ports for specific network services (critical for Active Directory domain controllers). |
## **4. Configuring DNS Server Settings**
- **Forwarders & Root Hints:** Forwarders pass unresolved queries to external or specific servers, whereas root hints provide a preconfigured list pointing to Internet root servers via Cache.dns. 

- **Round Robin:** Provides load sharing among mirrored services by rotating the order of multiple IP addresses associated with a single hostname. 

## **5. DNS Security Features**
- **DNSSEC:** Uses digital signatures (zone signing) to provide origin authentication, data integrity, and authenticated denial of existence. 

- **DNS Socket Pool & Cache Locking:** The socket pool randomizes source ports to protect against cache poisoning, while cache locking prevents cached records from being overwritten before their TTL expires. 

- **Response Rate Limiting (RRL) & DANE:** RRL mitigates DNS amplification DDoS attacks, and DANE utilizes TLSA records to prevent man-in-the-middle certificate attacks. 

## **6. Azure DNS and Hybrid Integration**
- **Azure Private DNS Zones:** Provide name resolution for internal Azure resources with private IP addresses within virtual networks. 

- **Virtual Network Linking:** Links virtual networks to private DNS zones, supporting auto-registration of VMs as A records. 

- **Hybrid Integration:** Resolving Azure DNS names from an on-premises network requires intersite virtual network connectivity, an Azure VM acting as a DNS forwarder, and proper VNet DNS configurations.


