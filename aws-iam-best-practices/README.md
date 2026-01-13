# AWS IAM Best Practices

This repository demonstrates AWS Identity and Access Management (IAM) best practices
using diagrams, policy examples, and real-world security patterns.

## Objectives
- Enforce least privilege access
- Eliminate long-term credentials
- Secure human and service access
- Enable scalable, auditable IAM architecture

---

## IAM Architecture Overview

![IAM Architecture](diagrams/iam-architecture.png)

### Key Design Principles
- No root account usage
- No IAM users for applications
- Role-based access using STS
- Mandatory MFA for human access
- Permission boundaries for admin roles
- Cross-account access using AssumeRole

---

## IAM Best Practices Implemented

### 1. Least Privilege
Policies grant only required actions and resources.

## Good: Policy
Json
{
  "Effect": "Allow",
  "Action": ["s3:GetObject"],
  "Resource": "arn:aws:s3:::example-bucket/*"
}

## Bad: Policy
Json

{
  "Effect": "Allow",
  "Action": “*”,
  "Resource": “*”
}

