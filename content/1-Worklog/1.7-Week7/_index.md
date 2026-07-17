---
title: "Week 7"
date: 2026-06-07
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

**Weekly objectives:**
- Attend the AWS First Cloud AI Journey Community Day technology event.
- Write a reflection report and blog sharing event learnings.
- Research advanced Amazon S3 features: static website hosting and versioning.
- Configure S3 Cross-Region Replication (CRR) for data redundancy.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Networked with local AWS community engineers and collected technology insights. | Jun 08 |
| Tuesday | Wrote a technical event summary and published a blog post sharing community day learnings. | Jun 09 |
| Wednesday | Researched Amazon S3 static website hosting, Object Versioning, and S3 lifecycle transit policies. | Jun 10 |
| Thursday | Configured Cross-Region Replication (CRR) on a test S3 bucket, verifying copy replication to another AWS Region. | Jun 11 |
| Friday | Perform validation tests on object restoration lifecycle rules inside the replication bucket. | Jun 12 |
| Saturday | Attended the AWS First Cloud AI Journey Community Day technology event in Ho Chi Minh City. | Jun 13 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Collected feedback on Capstone architectural ideas from senior AWS solutions architects.
  - Lesson: Networking with community developers reveals common pitfalls in distributed database replication.
- **Tuesday:**
  - Result Achieved: Published learning blog on personal portfolio website, detailing security and ML pipeline concepts.
  - Lesson: Documenting concepts helps solidify learning and contributes back to the developer community.
- **Wednesday:**
  - Result Achieved: Understood bucket policy requirements to expose static frontend assets to public users securely.
  - Lesson: Enabling object versioning protects against accidental deletes by keeping historical file revisions.
- **Thursday:**
  - Result Achieved: Verified files uploaded to source region replicate to destination region bucket automatically.
  - Lesson: CRR requires versioning enabled on both source and destination buckets, incurring cross-region transit costs.
- **Friday:**
  - Result Achieved: Verified that replica objects are properly archived according to the defined lifecycle rules.
  - Lesson: Establishing validation checks ensures disaster recovery readiness.
- **Saturday:**
  - Result Achieved: Connected with local cloud community leaders and explored generative AI solution models.
  - Lesson: Direct interaction with domain experts accelerates comprehension of complex AWS architectures.
