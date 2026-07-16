---
title: "Week 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# Work Log: Advanced Cost Control, Automated Alerting Systems, and Core Infrastructure Principles

> **Week 2 - Monday, June 08, 2026:** Configured a multi-layered cost tracking system, established an operational emergency response runbook, and studied AWS global infrastructure and cloud security theory.

---

### Objectives for the Week

- Implement a **Multi-Tiered Cost Alerting Framework** to secure the account.
- Enable **AWS Cost Anomaly Detection** and establish standardized resource tagging rules.
- Document an **Emergency Cost Control Protocol** using AWS CLI commands to audit active resources.
- Study foundational AWS concepts: Shared Responsibility Model, IAM, Global Infrastructure, and storage/database architectures.

---

### Billing Safeguards & Cost Monitoring Systems

#### 1. Designing 3-Tier Budget Thresholds via AWS Budgets

To keep promotional credit consumption under control and prevent unexpected charges, I created three separate budgets:

| Alert Identity | Budget Limit | Notification Conditions |
|---|---|---|
| **Monthly Cap Budget** | $40.00 / month | Alert when actual spend reaches **80% ($32.00)** |
| **Warning Budget** | $20.00 / month | Alert when actual spend reaches **50% ($10.00)** |
| **Daily Safeguard Budget** | $5.00 / day | Alert when actual spend reaches **100% ($5.00)** |

The daily budget acts as a rapid defense check, enabling detection of misconfigured or runaway resources within 24 hours instead of letting billing accumulate until the end of the month.

#### 2. CloudWatch Billing Alarms

I set up Billing Alarms within Amazon CloudWatch and configured Amazon SNS to route notifications based on threat levels:

| Spending Level | Notification Channel | Recovery Action |
|---|---|---|
| **$15.00** | Personal Email | Low priority; review active resources. |
| **$35.00** | Email + SMS Alert | Medium priority; check resource scaling and workloads. |
| **$60.00** | Email + SMS + Discord Webhook | Critical priority; execute immediate resource teardown. |

#### 3. AWS Cost Anomaly Detection

Activated the **AWS Cost Anomaly Detection** service, which uses machine learning to monitor spending behavior and spot unusual spikes:
- Monitor Scope: All AWS Services.
- Alert Threshold: Cost anomaly impact exceeding $5.00 daily.
- Benefit: Sends prompt notification when anomalous spending is identified, independent of traditional static budget metrics.

---

### Resource Tagging Rules & Consolidated Dashboards

#### Standardized Resource Tagging Policy

To organize billing reports in AWS Cost Explorer, all provisioned resources must have the following tags:

| Tag Key | Example Value | Description |
|---|---|---|
| `Project` | `cloud-training` | Associates resources with a specific project or lab. |
| `Environment` | `dev` / `testing` | Differentiates sandbox/development assets from testing environments. |
| `Author` | `intern-dev` | Identifies the team member responsible for the resource. |

#### Integrated CloudWatch Dashboard

- Built a consolidated **CloudWatch Monitoring Dashboard** displaying EC2 instance CPU metrics alongside estimated monthly charges.
- Monitored application metrics to avoid runaway loops in test scripts that could drain credits.

---

### Emergency Resource Teardown & CLI Runbook

#### 1. CLI Commands for Fast Resource Detection

If an alert triggers, run the following CLI commands in the terminal to quickly audit active, costly resources:

```bash
# 1. List all running EC2 instances in the current Region
aws ec2 describe-instances --filters "Name=instance-state-name,Values=running" \
  --query 'Reservations[].Instances[].{ID:InstanceId,Type:InstanceType,Zone:Placement.AvailabilityZone}' \
  --output table

# 2. View all active RDS database instances
aws rds describe-db-instances \
  --query 'DBInstances[].{DBIdentifier:DBInstanceIdentifier,Engine:Engine,Status:DBInstanceStatus}' \
  --output table

# 3. Locate unattached EBS volumes (which continue to charge for storage even if the EC2 instance is terminated)
aws ec2 describe-volumes --filters "Name=status,Values=available" \
  --query 'Volumes[].{VolumeID:VolumeId,Size:Size,Zone:AvailabilityZone}' \
  --output table

# 4. Identify unassociated Elastic IP addresses (which incur hourly idle fees)
aws ec2 describe-addresses \
  --query 'Addresses[?AssociationId==null].{IP:PublicIp,AllocationId:AllocationId}' \
  --output table
```

#### 2. Emergency Shutdown Runbook
1. Sign in to the AWS Management Console immediately.
2. Stop or terminate active `EC2` virtual servers and delete idle database instances (`RDS`).
3. Delete unattached `EBS` volumes and release unassociated `Elastic IP` addresses.
4. Disable active foundation model playbooks on Bedrock and delete obsolete Lambda routes.

---

### Theoretical Cloud Architecture Concepts

#### Cloud Models & Characteristics
- **Elasticity:** The ability to scale system capacity up or down dynamically based on user demand.
- **Financial Flexibility:** Transitioning from upfront hardware expenses (CapEx) to variable operational costs paid per use (OpEx).
- **Global Reach:** Deploying application components in multiple locations worldwide with low latency.

| Service Model | AWS Example | User Responsibility |
|---|---|---|
| **IaaS (Infrastructure as a Service)** | Amazon EC2, VPC | Operating system management, network settings, runtime environments, and code. |
| **PaaS (Platform as a Service)** | AWS Elastic Beanstalk, RDS | Application code deployment and database schema design. |
| **SaaS (Software as a Service)** | Amazon WorkMail, Chime | Access and use the software directly via web browser; zero system maintenance. |

#### AWS Global Infrastructure
- **Regions:** Geographically isolated areas containing multiple data centers. Data remains in the designated region unless manually replicated.
- **Availability Zones (AZs):** Physically isolated datacenters inside a Region, connected by low-latency fiber links. Deploying across multiple AZs yields **High Availability**.
- **Edge Locations:** CDN nodes (Amazon CloudFront) that cache static web assets near end-users to reduce load times.

---

### Security, Identity, & Access Management (IAM)

- **The Shared Responsibility Model:**
  - **AWS Responsibility (Security OF the cloud):** Securing global physical datacenters, host hardware, virtualization layers, and network components.
  - **Customer Responsibility (Security IN the cloud):** Operating system patching, firewall rules (Security Groups), IAM policies, and data encryption.
- **IAM Identity Best Practices:**
  - **Secure the Root Account:** Enable Multi-Factor Authentication (MFA) and avoid using root for daily administration.
  - **Principle of Least Privilege:** Provide users only the minimal credentials needed for their specific tasks.
  - **Group-Based Governance:** Assign permissions to IAM Groups rather than individual users.
  - **JSON Policy Documents:** Define granular permissions (Allowed Actions, Resources, and Conditions) using structured JSON files.

---

### Storage & Database Service Overview

- **Amazon S3 (Simple Storage Service):**
  - Durable object storage designed to achieve **99.999999999% (11 nines) durability**.
  - Supports automatic lifecycle rules (S3 Standard, Standard-IA, Glacier) to lower costs for infrequently accessed data.
- **Amazon RDS:** Managed database service handling automated backups, minor security patches, and replication setups.
- **AWS Lambda:** Serverless computing service that executes code in response to events, scaling resources automatically.

---

### Study Schedule & Topics Completed

| Study Date | Core Topic Focus | Primary AWS Services Involved |
|---|---|---|
| **08/06/2026** | Compute Infrastructure & Instance Provisioning | Amazon EC2, AMI, Instance Types |
| **08/06/2026** | Access Controls & Identity Management | AWS IAM, Roles, Policies |
| **08/06/2026** | Cloud Development IDE environments | AWS Cloud9, Instance Profiles |
| **08/06/2026** | Object Storage & Hosting configurations | Amazon S3, S3 Bucket Policies |
| **08/06/2026** | Database Deployment & Administration | Amazon RDS, DB Engines |

---

### Key Takeaways from Week 2

1. **Layered Billing Security:** Using a combined approach of budgets, CloudWatch alarms, and Machine Learning anomaly detection is highly effective for preventing high AWS bills.
2. **Resource Tagging Discipline:** Tagging resources is essential for cloud financial management and identifying the source of unexpected costs.
3. **Operational Preparedness:** Knowing how to use AWS CLI commands to audit idle resources (such as unattached EBS volumes or unassigned Elastic IPs) is an essential skill for managing cloud operations.

---

*Reference: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
