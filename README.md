# aws-cloud-operations-lab
Secure AWS environment built via CLI — VPC, EC2, S3, CloudWatch, CloudTrail, SSM

**Type:** Hands-On Self-Study Project
**Cert target:** AWS Certified SysOps Administrator Associate (SOA-C02)

## What Was Built

A secure, production-style AWS environment deployed entirely via AWS CLI:

- Custom VPC with public/private subnet separation, Internet Gateway, NAT Gateway, and route tables enforcing network isolation
- EC2 instance in a private subnet — no public IP, no open ports, accessed only via SSM Session Manager
- S3 bucket with versioning, AES-256 server-side encryption, and all public access blocked
- CloudWatch log group with 30-day retention policy and CPU threshold alarm
- CloudTrail trail capturing all account-level API activity and delivering logs to a dedicated S3 bucket

## Architecture

```
Internet → Internet Gateway → Public Subnet (10.0.1.0/24)
                                  └── NAT Gateway
                              Private Subnet (10.0.2.0/24)
                                  └── EC2 (SSM only, no public IP)
S3 Bucket ← versioning + AES-256 encryption + Block Public Access
CloudWatch ← log group + CPU alarm
CloudTrail ← full API audit log → S3
```

## Tools & Services

AWS CLI · IAM · EC2 · VPC · S3 · CloudWatch · CloudTrail · SSM Session Manager

## Screenshots

See the `screenshots/` folder for evidence of every resource configured — IAM, VPC, subnets, route tables, NAT Gateway, EC2, security groups, SSM session, S3 versioning, CloudWatch alarms, and CloudTrail events.
