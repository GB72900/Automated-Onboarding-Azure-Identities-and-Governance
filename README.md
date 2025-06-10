# Automated-Onboarding-Azure-Identities-and-Governance
Azure Logic App to automate onboarding of new hires via email, user provisioning, and tagging.
It **parses incoming email**, **creates a user**, **adds to a security group**, applies **resource provisioning** (via ARM template), and **sends a welcome email**.

## Table of Contents
- [How it Works](#how-it-works)
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

## Setup & Deployment

1. **Clone the repository**  
   ```bash
   git clone https://github.com/GB72900/Automated-Onboarding-Azure-Identities-and-Governance.git
   cd Automated-Onboarding-Azure-Identities-and-Governance
2. **Import the Logic App**
   - Go to Azure Portal → Logic Apps → Create from custom template
   - Upload: `LogicApps/NewHireOnboarding.json`

3. **Deploy the ARM Template**
   - Go to Resource Group → Deploy a custom template
   - Upload: `ARM-Templates/OnboardingResources.json`

4. **Authenticate Logic App Connectors**
   - Ensure each action (Create User, Send Email, etc.) is signed in with the correct Azure or Microsoft 365 account.

5. **Test it**
   - Send an email with a JSON body like:
     ```json
     {
       "Name": "Randy Swimming",
       "Title": "Software Engineer",
       "Department": "Engineering"
     }
## Usage

Once deployed:

- Logic App listens for new hire emails
- Automatically:
  1. Parses incoming email
  2. Creates user in Azure AD
  3. Adds user to a security group
  4. Applies ARM-based provisioning (e.g., tagging VM)
  5. Sends a welcome email to the new user
## Prerequisites

- Azure subscription with Logic Apps enabled
- Global Admin or User Admin access in Azure AD
- Mailbox monitored by Logic App
- Proper permissions to create users, manage groups, and deploy resources

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License.





