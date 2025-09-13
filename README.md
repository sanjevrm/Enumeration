# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
## SITE:
<img width="1563" height="1195" alt="image" src="https://github.com/user-attachments/assets/9b834999-515b-40c2-94dd-9bddbdf47bbe" />

## INURL:
<img width="1442" height="1145" alt="image" src="https://github.com/user-attachments/assets/b1142e63-2b6b-4ca1-b20c-c6df69bf2867" />

## INTITLE:
<img width="1405" height="1199" alt="image" src="https://github.com/user-attachments/assets/7dec65f2-56ad-45bb-a3ad-dd59ba8db641" />

## FILETYPE:
<img width="1398" height="1192" alt="image" src="https://github.com/user-attachments/assets/e46c5189-b59c-4606-b33d-297ac49922fb" />

## INTEXT:
<img width="1490" height="1199" alt="image" src="https://github.com/user-attachments/assets/3e4494aa-1fb4-4663-b2a0-d62a2e0a1577" />

## LINK:
<img width="1425" height="1199" alt="image" src="https://github.com/user-attachments/assets/2fd33031-9e0b-4940-b35a-2116a1279bae" />

## CACHE:
<img width="1467" height="1199" alt="image" src="https://github.com/user-attachments/assets/8c007980-4100-48c9-a5b0-fd6817dce0d1" />

## EXT:
<img width="1433" height="1199" alt="image" src="https://github.com/user-attachments/assets/c1f0da81-819a-4a99-9683-8515a1c79d88" />

# DNS Enumeration
<img width="744" height="783" alt="image" src="https://github.com/user-attachments/assets/698d4913-9526-431a-9b7a-04e49f7a9050" />

## DNS Recon
<img width="623" height="500" alt="image" src="https://github.com/user-attachments/assets/6d95fa9a-fc7e-4ddd-9f35-78adffd1628d" />

| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


# OUTPUT:
## NSLOOKUP:
<img width="523" height="761" alt="image" src="https://github.com/user-attachments/assets/21db3ca7-0401-4400-ada9-60dd041bb3c4" />

## DIG:
<img width="611" height="591" alt="image" src="https://github.com/user-attachments/assets/024801b7-8325-4ff7-b7f2-237266ce36be" />

## HOST:
<img width="596" height="396" alt="image" src="https://github.com/user-attachments/assets/8a37cf5f-9c58-41be-9a26-23ba80884317" />

## DNSENUM:
<img width="748" height="525" alt="image" src="https://github.com/user-attachments/assets/876bf839-d190-407e-b2ce-35dfb1f72d54" />

## DNSRECON:
<img width="579" height="493" alt="image" src="https://github.com/user-attachments/assets/9348664c-647d-4659-bcff-eaa9f06e04fc" />

## FIERCE:
<img width="617" height="881" alt="image" src="https://github.com/user-attachments/assets/ece6468a-89f5-438e-8cee-ae888086e506" />

## Harvestor:
<img width="597" height="565" alt="image" src="https://github.com/user-attachments/assets/a37a4f56-bff3-4157-987e-e420328b8bdc" />

## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:
<img width="702" height="440" alt="image" src="https://github.com/user-attachments/assets/c647456b-bc5d-4a3b-9120-2a16c0e3d174" />



## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
  <img width="657" height="380" alt="image" src="https://github.com/user-attachments/assets/985467fe-1f84-4958-b588-ddc0ce2b10b4" />



## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:

<img width="703" height="106" alt="image" src="https://github.com/user-attachments/assets/6244e3b3-8784-4c67-a153-cfd5e234774c" />


## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
