---
title: "Week 2"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

**Weekly objectives:**
- Explore the AWS Management Console interface, AWS CLI, and CloudShell tool.
- Research cloud security management and Multi-Factor Authentication (MFA/2FA) configurations.
- Understand the differences between IAM Policies and IAM Roles for security access control.
- Master the theoretical knowledge of Module 02 on AWS Global Infrastructure.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Explored the AWS Management Console layout and researched the AWS Global Infrastructure layout. | Apr 27 |
| Tuesday | Installed the AWS CLI package on local machine, configured security credentials, and launched CloudShell sessions. | Apr 28 |
| Wednesday | Configured virtual Multi-Factor Authentication (MFA) on the Root Account using Google Authenticator. | Apr 29 |
| Thursday | Studied IAM Policies, IAM Roles, and JSON policy structures. Designed a custom policy template. | Apr 30 |
| Friday | Created a developer IAM User account, assigned it to an administrator group, and tested access restrictions. | May 01 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Familiarized with service search, region selector, and dashboard layout. Completed Module 02 theory.
  - Lesson: AWS Regions contain multiple isolated AZs to prevent concurrent regional outages.
- **Tuesday:**
  - Result Achieved: Verified connection between local CLI tool and AWS Cloud using access key credentials.
  - Lesson: CloudShell abstracts browser terminal setups and runs command queries with current credentials automatically.
- **Wednesday:**
  - Result Achieved: Root account secured with dual authentication parameters. Verified login flow.
  - Lesson: Root accounts should never be used for daily operational tasks; restrict its usage to billing changes.
- **Thursday:**
  - Result Achieved: Learned how JSON documents specify Effect, Action, Resource, and Condition arguments.
  - Lesson: Policies grant explicit access rules to users, while Roles are assumed by compute instances or services.
- **Friday:**
  - Result Achieved: Successfully restricted root usage by shifting daily cloud workflows to the newly created developer IAM User.
  - Lesson: Applying the principle of least privilege ensures users only access resources critical to their job description.
