---
title: "Week 12"
date: 2026-07-12
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

**Weekly objectives:**
- Develop Glassmorphism Web Portal dashboard using React and Node.js.
- Deploy web portal to Ubuntu EC2 server, running background PM2 process.
- Configure Nginx reverse proxy to route port 80 traffic to internal port.
- Secure web portal domain using Let's Encrypt SSL certificates via Certbot.
- Conduct End-to-End integration testing across multiple user roles.

**Tasks to be deployed this week:**

| Day | Task | Date |
|---|---|---|
| Monday | Programmed the ReactJS frontend dashboard, integrating Plotly.js charts displaying actual vs forecast sales. | Jul 12 |
| Tuesday | Provisioned production Ubuntu EC2 instance. Cloned codebase, configured environment variables, and configured PM2 runtime. | Jul 12 |
| Wednesday | Installed and configured Nginx reverse proxy server policies on the production Ubuntu instance. | Jul 12 |
| Thursday | Configured domain settings, ran Certbot Let's Encrypt client utilities to generate secure SSL certificates. | Jul 12 |
| Friday | Conducted End-to-End integration testing across multiple user roles (Associate, Store Manager, Admin). Finalized reports. | Jul 12 |

**Weekly results achieved:**
- **Monday:**
  - Result Achieved: Created interactive UI dashboard displaying store maps and stockout alert warning flags.
  - Lesson: Using glassmorphism theme components enhances UI visual appeal and user experience.
- **Tuesday:**
  - Result Achieved: Application running continuously in the background. PM2 auto-restart policy enabled.
  - Lesson: PM2 manages processes continuously, preventing server crashes from taking the web application offline.
- **Wednesday:**
  - Result Achieved: Incoming port 80 traffic mapped successfully to internal port 3000 backend application services.
  - Lesson: Using Nginx as a reverse proxy protects node applications by abstracting backend port exposures.
- **Thursday:**
  - Result Achieved: Secure SSL certificates installed. Nginx auto-redirects port 80 requests to encrypted port 443 routes.
  - Lesson: Securing web endpoints with SSL is mandatory to protect sensitive user login tokens from transit sniffing.
- **Friday:**
  - Result Achieved: Confirmed correct permission controls and prediction visualization accuracy. Submitted final internship reports.
  - Lesson: End-to-end testing validates correct system behaviors before presenting final deliverables to stakeholders.
