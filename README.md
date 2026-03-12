# Pki-secure-web-infrastructure-gns3

## Overview

This project demonstrates the implementation of a secure web infrastructure using a private Public Key Infrastructure (PKI) in a simulated enterprise network environment.

A custom Certificate Authority (CA) was created to issue trusted certificates for an internal web server. The project shows how secure HTTPS communication can be established using certificates issued by a private CA.

The network environment was built using GNS3 to simulate a segmented enterprise architecture with internal networks, DMZ, and firewalls.

---

## Technologies Used

- GNS3
- OpenSSL
- Apache HTTP Server
- Linux (Ubuntu)
- TLS / HTTPS
- Public Key Infrastructure (PKI)

---
## Network Architecture
The network infrastructure was designed to simulate a real enterprise environment with segmented networks.

The topology includes:

- External Network
- Perimeter Firewall
- Internal Firewall
- DMZ Network
- Server LAN
- Corporate LAN

The Certificate Authority (CA) and the internal web server were deployed inside the Server LAN.

### Network Topology
<img width="1160" height="636" alt="Screenshot 2026-03-13 at 07 31 18" src="https://github.com/user-attachments/assets/ebb93c45-037f-4cb9-9eb7-e29627affff6" />


---

## Server LAN Infrastructure

The Server LAN contains the internal services required for secure communication.

Components include:

- DNS Server
- Internal Web Server
- Certificate Authority (CA)

The CA is responsible for issuing certificates to the web server.

---

## Certificate Authority (CA) Configuration

A private Certificate Authority was configured to generate and sign certificates.

The CA performs the following tasks:

1. Generates a root certificate.
2. Signs certificate requests from servers.
3. Issues trusted certificates for HTTPS communication.

### CA Network Configuration
<img width="1440" height="900" alt="Screenshot 2026-03-13 at 07 31 37" src="https://github.com/user-attachments/assets/9fb974b7-7d82-44c6-aba2-f16b2ed026a3" />

---

## Internal Web Server Configuration

An internal web server was deployed to host a secure website.

The server performs the following steps:

1. Generates a public/private RSA key pair.
2. Creates a Certificate Signing Request (CSR).
3. Sends the CSR to the Certificate Authority.
4. Receives a signed certificate from the CA.
5. Deploys the certificate for HTTPS communication.

### Web Server Network Configuration

<img width="1440" height="900" alt="Screenshot 2026-03-13 at 07 31 41" src="https://github.com/user-attachments/assets/16c2b3a5-549c-4f31-bcd0-1e920db71119" />



---

## HTTPS Deployment

The web server was configured using Apache HTTP Server to enable HTTPS communication.

Steps performed:

1. Install Apache web server.
2. Configure VirtualHost for HTTPS.
3. Install signed certificate and private key.
4. Enable SSL module.
5. Restart Apache service.

The server hosts a simple test webpage to verify HTTPS functionality.

---

## Client Access and Trust Configuration

Clients within the Corporate LAN can access the secure web server.

To establish trust:

1. The root CA certificate is installed on client systems.
2. The client browser verifies the server certificate.
3. A secure HTTPS connection is established.

---

## Security Concept Demonstrated

This project demonstrates how Public Key Infrastructure establishes trust in secure communications.

The certificate verification process ensures that the client can confirm the identity of the server before exchanging encrypted data.

This helps mitigate attacks such as Man-in-the-Middle attacks where attackers attempt to intercept communication between clients and servers.

---

## What I Learned

Through this project I gained practical experience with:

- Public Key Infrastructure (PKI)
- Certificate Authorities
- TLS/HTTPS configuration
- Certificate Signing Requests (CSR)
- Apache HTTPS server configuration
- Secure network architecture
- Network simulation using GNS3






