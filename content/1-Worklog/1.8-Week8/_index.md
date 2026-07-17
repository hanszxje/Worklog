---
title: "Week 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Weekly objectives:**
- Study AWS Disaster Recovery strategies based on RTO and RPO metrics.
- Compare DR deployment models: Backup/Restore, Pilot Light, Warm Standby, Multi-Site.
- Deploy Amazon FSx for Windows File Server Multi-AZ.
- Integrate Microsoft Active Directory directory services with file servers.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Studied Disaster Recovery (DR) models, focusing on defining Recovery Time Objective (RTO) and Recovery Point Objective (RPO). | Jun 08 |
| Tuesday | Compared architectural differences between Backup/Restore, Pilot Light, Warm Standby, and Multi-Site DR topologies. | Jun 09 |
| Wednesday | Executed Lab 25, initiating the creation of an Amazon FSx for Windows File Server instance with Multi-AZ layout. | Jun 10 |
| Thursday | Configured AWS Directory Service, setting up a Microsoft Active Directory server domain to join FSx. | Jun 11 |
| Friday | Reviewed AWS security best practices: database encryption via KMS keys and user pools using Cognito. | Jun 12 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Defined target metrics: RTO (allowable downtime duration) and RPO (allowable data loss duration).
  - Lesson: Lowering RTO/RPO requires active-active systems, which exponentially increases AWS resource costs.
- **Tuesday:**
  - Result Achieved: Understood trade-offs: Pilot Light keeps database active while compute servers remain scaled down.
  - Lesson: Choosing the right DR strategy depends on the business's budget and system critical level.
- **Wednesday:**
  - Result Achieved: Initialized shared Windows file system distributed across two separate Availability Zones.
  - Lesson: Multi-AZ FSx provides automatic failover capabilities, ensuring files remain accessible during primary zone failure.
- **Thursday:**
  - Result Achieved: Joined FSx file system to the active directory domain, enabling centralized user credential control.
  - Lesson: Active Directory integration simplifies credential management by mapping corporate login accounts to S3/FSx structures.
- **Friday:**
  - Result Achieved: Learned how Cognito manages sign-up flows and KMS handles customer managed encryption keys.
  - Lesson: KMS enables transparent encryption of database storage, while Cognito decouples identity management from application logic.
