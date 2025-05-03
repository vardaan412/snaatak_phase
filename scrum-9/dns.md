
# DNS Documentation

<div align="center">
  <img src="https://www.lifewire.com/thmb/xVHr44B8fqTlF6aG8nk3Sp-aMDM=/2644x1133/filters:fill(auto,1)/GettyImages-585297068-52005387a57248a19e3ee29bc1af44b4.jpg" alt="Ansible Logo" width="40%"/>
</div>

| Created     | Last updated | Version | Author         | Comment | Reviewer |
|-------------|-----------|---------|----------------|---------|----------|
| 03-05-2025  | 03-05-2025 | V1.0  | Vardaan Saxena |     Internal Review    | Pritam    |


  
  ## Table of Content
- [Introduction](#introduction)
- [Why DNS ?](#why-dns)
- [What is DNS ?](#what-is-dns)
- [Types of records](#types-of-records)
- [How it is work ?](#how-it-is-work)
- [How to get domain ?](#how-to-get-domain)
- [Different DNS provider](#different-dns-provider)
- [Comparision between DNS providers](#comparision-between-dns-providers)
- [Contact information](#contact-information)
- [References](#references)



## Introduction
> The Domain Name System (DNS) is like the internet’s phone book. It helps you find websites by translating easy-to-remember names (like www.example.com) into the numerical IP addresses (like 192.0.2.1) that computers use to locate each other on the internet. Without DNS, you would have to remember long strings of numbers to visit your favorite websites. 

## Why DNS ?

> Without DNS, we’d have to remember long numbers (IP addresses) for every website, which would be hard and confusing. DNS makes the internet easy to use by letting us type website names instead of numbers.

## What is DNS ? 
> The Domain Name System (DNS) works like the internet's phonebook. When you type a web address like "google.com" or "nytimes.com" into a browser, DNS helps find the right IP address for that website. The browser then uses this IP address to connect to the website's server and load the page. DNS servers are the computers that respond to these requests, helping browsers find the right websites quickly.

## Types of records

 - **A (Address) Record:** Maps a domain name to an IPv4 address.

 - **AAAA (IPv6 Address) Record:** Maps a domain name to an IPv6 address

 - **CNAME (Canonical Name) Record:** Maps a domain name (alias) to another domain name.

 - **MX (Mail Exchange) Record:** Directs email to mail servers for a domain.

 - **TXT (Text) Record:** Provides arbitrary text data for a domain. 

 - **SOA (Start of Authority) Record:** Contains administrative information about the domain.


## How it is work ? 
<div align="center">
  <img src="https://heimdalsecurity.com/blog/wp-content/uploads/www.heimdalsecurity.com_-1.png" alt="Ansible Logo" width="60%"/>
</div>

### DNS Recursor (or Resolver): 
> This is like a "helper" that looks up the website address for you. When you want to visit a website, it asks other servers to find the correct IP address that leads to the website.
### Root Nameservers: 
> These are the starting points of the DNS system. They help by pointing the resolver to the right type of server based on the website’s domain (like ".com", ".org", etc.).
### TLD Nameservers :
> These servers manage the domain extensions like ".com", ".org", and so on. They tell the resolver where to find the next server that knows the website’s exact IP address.
### Authoritative Nameservers:
> These are the "final answer" servers. They have the exact IP address for the website you're looking for. There are two types:

    Master (Primary): The main server that holds the original IP records.
    Slave (Secondary): A backup server that has a copy of the information in case the master server fails.

## How to get domain ?

**For detailed information How to get Domain and how to use Domnin please refer to the following resources**
| Link         | Description         |
|--------------|------------------------|
| [Domain]() |POC of Domain name system.| 


## Different DNS provider 

| DNS Providers       | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Namecheap           | Easy-to-use DNS management, includes free DNS with domain registration.     |
| Amazon Route 53     | Good for complex setups, like apps on Amazon Web Services.                  |
| Google Public DNS   | Very fast, free, and trusted.                                               |
| GoDaddy             | Popular for domain registration and DNS management, with additional services like website hosting and email. |


## Comparision between DNS providers

| DNS Providers       | Key Features                                                                 | Speed  | Security           | Pricing                                                              |
|---------------------|-------------------------------------------------------------------------------|--------|---------------------|----------------------------------------------------------------------|
| **Namecheap**        | Easy-to-use interface, free DNS with domains, supports dynamic DNS, great support | High   | DDoS protection      | **Free DNS with domain; Premium DNS available at affordable pricing** |
| Google Public DNS   | Fast, low-latency DNS                                                         | High   | Basic (no advanced security features) | Free                                                                |
| Amazon Route 53     | Scalable, integrates with AWS, advanced routing policies                      | High   | DDoS protection      | Pay-as-you-go (based on queries and services used)                   |
| GoDaddy             | Domain registration and DNS, integrated with hosting services                 | Medium | DDoS protection      | Paid (pricing depends on domain and hosting plan)                    |



## Contact Information
| **Name**    | **Email address**         |
|-------------|---------------------------|
| Vardaan Saxena | vardaan.saxena.snaatak@mygurukulam.co    |



## References
| Description           | Link                                                                 |
|------------------------|----------------------------------------------------------------------|
| Introducing DNS        | [What is DNS – AWS](https://aws.amazon.com/route53/what-is-dns/)     |
| Working of DNS         | [How DNS Works – YouTube](https://youtu.be/vhfRArT11jc?si=3cYjikGF-gLjLbrf) |
| DNS Provider   | [Namecheap DNS](https://www.namecheap.com/domains/dns/)              |

