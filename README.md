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

# SITE

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bc86299b-7183-46f3-b915-4f99662aaf22" />

# INURL

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d7a0f085-bb29-4ebc-8bd0-0df65e492a71" />

# INTITLE:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c75dcb38-3123-4238-9abc-5c229fa6bf05" />

# FILETYPE

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f32e4726-4b7e-4468-b555-b928b5e19512" />

# INTEXT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6fe2e404-eb58-45d2-8140-385ca540a740" />

# LINK

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9316cf14-1fc7-482b-bde6-2749ef35386c" />

# CACHE

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/95e97d9e-509f-486f-a7ce-a223f16923bd" />

# EXT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dd4b572d-7a0c-4307-9d55-e0fe43224907" />

# DNS Enumeration

<img width="752" height="559" alt="image" src="https://github.com/user-attachments/assets/8c96c17d-8b74-4c33-9c55-2a35f56d5cf7" />

## DNS Recon

<img width="712" height="504" alt="image" src="https://github.com/user-attachments/assets/b240541a-fbec-478d-9317-b1686dd851fe" />

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


## OUTPUT:

## NSLOOkUP

<img width="478" height="786" alt="image" src="https://github.com/user-attachments/assets/0e065547-d87e-4266-ac57-db7c8f7979c8" />

## DIG

<img width="640" height="596" alt="image" src="https://github.com/user-attachments/assets/a8167b0c-e691-46df-95d0-36a8d274698a" />

## HOST

<img width="592" height="411" alt="image" src="https://github.com/user-attachments/assets/94afaa9a-18aa-4aa3-8da9-dedee4253d1c" />

## DNSSENUM 

<img width="716" height="536" alt="image" src="https://github.com/user-attachments/assets/19b78165-6213-46f9-8db9-7a5040036039" />

## DNSRECON

<img width="654" height="503" alt="image" src="https://github.com/user-attachments/assets/6eb76250-373c-4527-83d0-ca0e1032bf5e" />

## FIERCE

<img width="615" height="716" alt="image" src="https://github.com/user-attachments/assets/f19e8c7b-0f3f-4a56-a6f9-867c19c00f71" />

## HARVESTER

<img width="608" height="693" alt="image" src="https://github.com/user-attachments/assets/9b40843a-7234-4504-b83e-1ac27c8d7ac4" />

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

<img width="752" height="559" alt="image" src="https://github.com/user-attachments/assets/1a33d476-8ece-4288-9edd-d52acf6e9d33" />


## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
## Output
 
<img width="920" height="385" alt="image" src="https://github.com/user-attachments/assets/cb0a2695-3b47-40c2-8b44-f409b18c4c48" />


## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:

<img width="618" height="180" alt="image" src="https://github.com/user-attachments/assets/45d2221c-076f-4613-acb7-730573dd4582" />


## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
