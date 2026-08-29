# Cloudflare Zero Trust IAM Lab

A practical deployment demonstrating how to secure public-facing web infrastructure using Cloudflare Zero Trust, Identity and Access Management (IAM) controls, and Role-Based Access Control (RBAC). 

**Live Environment:** [Insert your .pages.dev link here]
*(Note: Access is restricted to authorized administrators only via Cloudflare Access).*

## Project Architecture 
This project simulates a secure corporate deployment pipeline, shifting the security perimeter from traditional network boundaries directly to the identity layer. 

* **Hosting & Deployment:** A static HTML environment deployed globally via Cloudflare Pages.
* **Version Control:** Continuous integration linked directly to this GitHub repository.
* **Security Perimeter:** Cloudflare Access acts as the Identity-Aware Proxy (IAP), placing a strict authentication wall in front of the application before any web traffic is routed to the origin server.

## Identity & Access Policy Configuration
To enforce the Principle of Least Privilege, I configured a custom Zero Trust policy that completely blocks unauthorized lateral movement. 

* **Default Action:** Deny (All traffic is blocked by default).
* **Identity Provider (IdP):** Configured One-Time PIN (OTP) via email to ensure seamless but secure authentication without relying on static passwords.
* **Authorized Identities:** Access is strictly governed by an "Include" rule, allowing only pre-approved administrator email addresses.
* **Audit Logging:** All successful and failed authentication attempts are logged by Cloudflare to provide visibility into identity-based threats.
