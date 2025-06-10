# Automated-Onboarding-Azure-Identities-and-Governance
Azure Logic App to automate onboarding of new hires via email, user provisioning, and tagging.
It **parses incoming email**, **creates a user**, **adds to a security group**, applies **resource provisioning** (via ARM template), and **sends a welcome email**.

## Table of Contents
- [How it Works](#how-it-works)
- [Repository Layout](#repository-layout)
- [Setup & Deployment](#setup--deployment)
- [Usage](#usage)
- [Prerequisites](#prerequisites)
- [Contributing](#contributing)
- [License](#license)

## How it Works
1. **Trigger**: New email arrives matching criteria.  
2. **Parse JSON**: Extract new hire details.  
3. **Create user** in Azure AD using the Logic App connector.  
4. **Add to group** for access control.  
5. **Provision resources** using an ARM template (e.g., VM, permissions).  
6. **Send Welcome Email** to the new hire.
## Repository Layout

## Setup & Deployment

1. **Clone the repository**  
   ```bash
   git clone https://github.com/GB72900/Automated-Onboarding-Azure-Identities-and-Governance.git
   cd Automated-Onboarding-Azure-Identities-and-Governance




