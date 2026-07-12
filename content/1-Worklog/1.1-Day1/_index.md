---
title: "Day 1"
date: 2026-06-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# Day 1 Log: Account Creation, Securing Credits, and Guided Hands-On Labs

> **Day 1 - Monday, June 01, 2026:** Registered for the AWS Educate/Student program, received initial credits, and finished 5 quick-start console labs to gain additional promo credits.

---

### Objectives for Today

- Successfully sign up for a personal AWS account and claim the **$100 introductory credit**.
- Complete **5 guided activities** on the AWS Console to earn **$100 more** ($20 reward per activity).
- Explore the console UI and learn the basic functionality of EC2, Bedrock, Budgets, Lambda, and RDS.
- Understand how to track costs and clean up resources immediately after use.

---

### Task 1: Provisioning a Virtual Machine via Amazon EC2 (Earned $20 Credit)

**Goal:** Create, test, and terminate a basic virtual server in the cloud.

**Service Overview:** **Amazon EC2 (Elastic Compute Cloud)** offers scalable compute resources in the cloud. Users can fully customize the operating system, compute power (RAM/CPU), and firewall settings.

**Steps Performed:**
1. Open the **AWS Console** → find the **Explore AWS** section on the home dashboard → select **Launch an instance using EC2**.
2. Press **Start activity** to launch the lab instructions.
3. Configure the virtual machine settings:
   - Name tag: Set it to `FCA-Test-Server`.
   - OS Image (AMI): Select Amazon Linux 2023 (Free Tier eligible).
   - Instance Type: Choose the default micro option (`t2.micro` or `t3.micro`).
4. Generate a cryptographic Key Pair for secure SSH connections:
   - Key pair name: `fca-keypair`
   - Key type: **RSA**
   - File format: **.pem** (download and store it locally).
5. Establish a Security Group with standard rules to permit basic web traffic.
6. Verify the summary options and click **Launch Instance**.
7. **Verification:** Go to the EC2 Instances page and ensure the instance transitions to **Running** and passes both **2/2 status checks**.
8. **Resource Teardown:** Select the instance → Instance State → Click **Terminate Instance** to delete the VM.

> **Key Takeaway:** Launching computing power on AWS is fast and simple. However, to prevent unintended charges, always terminate the instance immediately after your test, and confirm that the associated EBS storage volume is deleted as well.

---

### Task 2: Testing Generative AI Prompts on Amazon Bedrock Playground (Earned $20 Credit)

**Goal:** Interact with foundational LLMs on the AWS cloud environment.

**Service Overview:** **Amazon Bedrock** provides a single API to access high-performing foundation models from top AI developers (such as Anthropic, Meta, and Cohere) without needing to configure underlying servers.

**Steps Performed:**
1. Navigate to the **Amazon Bedrock Console** → choose the task **Use a foundation model in Amazon Bedrock**.
2. Request model access for **Claude 3 Haiku** (a fast, highly cost-efficient LLM).
3. If access is restricted, fill out the prompt requesting access with a brief use-case explanation.
4. Once access is granted, open the **Text Playground** and select **Claude 3 Haiku**.
5. Input a test prompt (e.g., "Summarize the top three benefits of cloud computing") and click **Run**.
6. Observe the model's output, experiment with configurations like Temperature (creativity level), and click **Finish** to complete.

> **Key Takeaway:** Using AI models on AWS requires complying with security policies. Providing a clear description of your intended use-case will speed up the model approval process.

---

### Task 3: Cost Management with AWS Budgets (Earned $20 Credit)

**Goal:** Build automated cost-alert thresholds to monitor spending.

**Service Overview:** **AWS Budgets** monitors your cloud spending and sends emails or SMS notifications when your actual or forecasted usage exceeds a specific budget limit.

**Steps Performed:**
1. Go to the **AWS Billing Console** → select **Budgets** → start the **Set up a cost budget using AWS Budgets** activity.
2. Select **Start activity** to run the budget creation wizard.
3. Input the budget details:
   - Budget Type: Cost Budget.
   - Period: Monthly.
   - Budget Limit: $20.00.
4. Set up the alerts:
   - Configure a notification when actual spending reaches **80% ($16.00)** of the budget.
   - Add your email address to receive the alerts.
5. Review the details and select **Create budget** to enable it.

> **Key Takeaway:** Setting up a cost budget is the primary safety measure for any AWS account. It helps you catch active resources before they use up all your promotional credits.

---

### Task 4: Deploying a Serverless Function with AWS Lambda (Earned $20 Credit)

**Goal:** Deploy and run a web backend using a serverless model.

**Service Overview:** **AWS Lambda** runs code in response to specific triggers (like HTTP requests) and manages the infrastructure automatically. You only pay for the exact execution time, and it scales to zero when idle.

**Steps Performed:**
1. Navigate to the **AWS Lambda Console** → select **Create a web app using AWS Lambda**.
2. Click **Start activity** → select **Use a blueprint** → find the **Getting started with Lambda HTTP** template.
3. Configure the serverless function:
   - Function name: `fca-http-lambda-app`
   - Check the box to allow AWS to create a new execution IAM Role with basic permissions.
4. Click **Create function** and wait for the deployment process to finish.
5. **Testing:** Copy the **Function URL**, paste it into a new browser tab, and verify that the function returns a JSON welcome message.
6. **Cleanup:** Delete the Lambda function to clean up the environment.

> **Key Takeaway:** Serverless computing eliminates server management tasks like OS patching. The application incurs zero charges when there is no incoming traffic.

---

### Task 5: Launching a Managed Relational Database via Amazon RDS (Earned $20 Credit)

**Goal:** Deploy and terminate a secure, managed database instance on AWS.

**Service Overview:** **Amazon RDS (Relational Database Service)** automates admin work like backups, software patching, and high-availability setups.

**Steps Performed:**
1. Open the **Amazon RDS Console** → choose the activity **Create an Amazon RDS Database**.
2. Use the **Easy create** option to apply optimized defaults.
3. Configure the database options:
   - Database Engine: Select **Aurora (PostgreSQL Compatible)**.
   - Instance Class: Choose the smallest available hardware tier.
4. Click **Create database** and wait for the status to change to **Available**.
5. **Cleanup Steps (Follow strict order):**
   - You cannot delete the database cluster while there are active instances inside.
   - First, select the database instance (`database-1-instance-1`) and delete it (uncheck the final snapshot option to speed up the process).
   - Once the instance is deleted, select and delete the parent DB cluster (`database-1`).

> **Key Takeaway:** Cloud database clusters have strict dependency relations. Always remove individual instances first before attempting to delete the parent cluster.

---

### Day 1 Summary & Key Lessons

- **Credits Claimed:** Obtained $100 starting credits and another $100 for finishing the 5 console tasks (Total: **$200**).
- **Core Skills:** Gained hands-on experience with foundational computing (EC2), AI prompting (Bedrock), cost guardrails (Budgets), serverless (Lambda), and relational databases (RDS).
- **Cost Awareness:** Built a habit of deleting resources immediately after testing. Forgetting to delete a database instance or virtual machine can exhaust your credits quickly.
- **Hands-on Learning:** Using the console's built-in guided activities is a safe, structured way to learn new cloud services.

---

*Reference: [First Cloud Journey - AWS Study Group](https://cloudjourney.awsstudygroup.com/)*
