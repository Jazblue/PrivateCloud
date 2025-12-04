# PrivateCloud
Serverless Private Network with Lambda &amp; DynamoDB

This project demonstrates a secure serverless architecture running inside a private VPC network.  
The application stores and retrieves data using a Lambda function that connects **privately** to DynamoDB using a **VPC Gateway Endpoint** with no public internet access.

## 🏗️ Architecture Overview

- **AWS Lambda** runs in a **private subnet**, isolated from the internet.
- **DynamoDB** is accessed using a **VPC Gateway Endpoint** (no NAT, no public traffic).
- **IAM Role** securely limits permissions to only required API actions.
- **CloudFormation** is used to provision all resources as code.

---

## 🔐 Key Security Principles

| Feature | Benefit |
|--------|---------|
| Lambda in Private Subnet | No public exposure or internet access |
| DynamoDB VPC Endpoint | Private, internal traffic only |
| Least Privilege IAM | Restricted access to only one table |
| No NAT Gateway | Lower cost + security by design |

---

---

## 🚀 Technologies Used

| Service | Purpose |
|---------|---------|
| AWS Lambda | Serverless compute |
| Amazon DynamoDB | NoSQL database |
| VPC + Private Subnets | Network isolation |
| VPC Gateway Endpoint | Private data access |
| IAM | Role-based access control |
| CloudFormation | Infrastructure as Code |

---

## 📦 Deployment Instructions (AWS CLI)

```bash
aws cloudformation deploy \
  --stack-name serverless-network \
  --template-file network-template.yaml \
  --capabilities CAPABILITY_NAMED_IAM \
  --region eu-west-2

This project demonstrates a private serverless architecture using Lambda, VPC, and DynamoDB. A VPC Gateway Endpoint is used to enable secure, private access to DynamoDB without requiring NAT or Internet Gateway resources. This pattern increases security and reduces costs.


