# Exploring AWS Services Lab - Solution

**Student Name:** France
**Date Completed:** 21 April 2026

---

## Exercise 1: Console Navigation

### Part A: Service Discovery

**EC2 (Compute):**
- Purpose: [It provides scalable virtual servers. The most common uses are for hosting applications, development and testing, batch processing, high performance computing and gaming.]
- Screenshot: ![EC2 Dashboard](screenshots/console-navigation/ec2-dashboard.png)

**S3 (Storage):**
- Purpose: [it is a storage service used to store and retrieve any amiunt of data from anywhere on the web.]
- Screenshot: ![S3 Dashboard](screenshots/console-navigation/s3-dashboard.png)

**RDS (Database):**
- Purpose: [It is a managed service used to set up, operate, and scale relational databases in the cloud.]
- Screenshot: ![RDS Dashboard](screenshots/console-navigation/rds-dashboard.png)

**VPC (Networking):**
- Purpose: [It is used to provision a logically isolated section of the AWS Cloud.]
- Screenshot: ![VPC Dashboard](screenshots/console-navigation/vpc-dashboard.png)

**IAM (Security):**
- Purpose: [It is used to manage user roles and who can access AWS resources.]
- Screenshot: ![IAM Dashboard](screenshots/console-navigation/iam-dashboard.png)

### Part B: Console Features

**Lambda Category:** [Compute]

**Pinned Services:**
![S3 Pinned](screenshots/console-navigation/s3-pinned.png)

**Recently Visited:**
![Recently Visited](screenshots/console-navigation/recently-visited.png)

**Region Selector:**
![Region Changed](screenshots/console-navigation/region-selector.png)
- Original region: [us-east-1]
- Changed to: [us-east-2]
- Changed back: [Yes]

---

## Exercise 2: Service Categorization

### Completed Service Matrix:

| Category | Services | Primary Use Case |
|----------|----------|------------------|
| Compute | [EC2, Lambda, Elastic Beanstalk, Fargate, lightsail, batch] | [Running applications, virtual servers, large-scale batch jobs, running serverless containers] |
| Storage | [S3, EBS, EFS, Storage Gateway, Snowball]| [Hybrid cloud storage, physical data migration, centralized backup management] |
| Database | [RDS, DynamoDB, ElastiCache, Redshift, Neptune] | [Managing data, Data warehousing] |
| Networking | [VPC, CloudFront, Route 53, Direct Connect, global Accelerator] | [Connecting resources, private connection, optimizing global performance, ] |
| Security | [IAM, KMS, CloudTrail, WAF, Secrets manager] | [Securing resources, filtering web traffic, rotating app credentials] |
| Management | [CloudWatch, CloudFormation, Systems Manager, Organizations, Trusted Advisor] | [Monitoring & automation, managing multiple accounts, optimizing best practices] |

### Research Question Answers:

**1. What's the difference between EC2 and Lambda?**

[EC2 is a virtual server (IaaS) and Lambda is a code execution service (PaaS)]

---

**2. When would you use S3 vs EBS?**

[S3 stores files such as videos, photos, logs, etc. while EBS is more for operating sustems and databases.]

---

**3. What's the difference between RDS and DynamoDB?**

[The data structure. For example RDS data are connected to each other on the other hand DynamoDB is data are non-relational.]

---

**4. Why do you need a VPC?**

[To create a private and secure isolation for cloud resources. Privacy from the world of my database and allows to connect office network to AWS securely.]

---

**5. What does CloudWatch monitor?**

[The performance and health of my resources and applications.]

---

## Exercise 3: AWS CLI

### CLI Version:
```
[aws-cli/2.34.4 Python/3.13.12 Darwin/24.6.0 source/x86_64]
```

### Configuration:
```
[NAME       : VALUE                    : TYPE             : LOCATION
profile    : <not set>                : None             : None
access_key : ****************YAW3     : shared-credentials-file : 
secret_key : ****************+wW6     : shared-credentials-file : 
region     : us-east-1                : config-file      : ~/.aws/config]
```

### CLI Outputs:

See attached `cli-outputs.txt` file for all command outputs.

**Key findings:**
- My AWS Account ID: 845587649055
- Default region: us-east-1
- Number of regions available: 17

---

## Exercise 4: Pricing Research

### Pricing Worksheet:

**1. EC2 t3.micro (Linux, us-east-1):**
- On-Demand: $0.0104 per hour
- Monthly (730 hours): $1.04
- Free Tier eligible: Yes
- Free Tier details: 750 hours/month 12 months

**2. S3 Standard Storage:**
- 100 GB monthly cost: $2.30
- Free Tier: First 5 GB free for 12 months
- Cost per GB: $0.023

**3. RDS db.t3.micro (MySQL):**
- Monthly cost: $12.41
- Storage (20 GB): $2.30
- Total: $14.71
- Free Tier eligible: Yes

**4. Data Transfer OUT:**
- 100 GB cost: $0
- First 100 GB free per month

### AWS Pricing Calculator Estimate:

![Pricing Calculator](screenshots/pricing-calculator.png)

**Estimate Link:** [[Paste your estimate link here]](https://calculator.aws/#/createCalculator/DataTransfer)

**Total Estimated Monthly Cost:** $0

---

## Exercise 5: Documentation Hunt

### EC2 Instance Types:
- Documentation URL: https://aws.amazon.com/ec2/instance-types/
- t3.medium vCPUs: 2
- t3.medium memory: 4 GB

### S3 Storage Classes:
- Documentation URL: [[URL]](https://aws.amazon.com/s3/storage-classes/)
- All storage classes:
  1. S3 Standard
  2. S3 Intelligent-Tiering
  3. S3 Standard-Infrequent Access
  4. S3 One Zone-Infrequent Access
  5. S3 Glacier Instant Retrieval
  6. S3 Glacier Flexible Retrieval
  7. S3 Glacier Deep Archive
  8. S3 Express One Zone
- Cheapest for archive: S3 Glacier Deep Archive

### IAM Best Practices:
- Documentation URL: [[URL]](https://aws.amazon.com/iam/resources/best-practices/)
- Three best practices:
  1. Grant Least Privilege
  2. Enable MFA
  3. Use Roles instead of IAM Users

### Free Tier Limits:
- Documentation URL: [[URL]](https://aws.amazon.com/free/)
- EC2 t2.micro hours/month: 750 hours
- S3 storage free: 5 GB

---

## Exercise 6: Regions and Availability Zones

### Your Current Region:
- Region Name: US East (N. Virginia)]
- Region Code: us-east-1]
- Number of AZs: 6

### Concept Questions:

**What is the difference between a Region and an Availability Zone?**

A Region is a physical geographic area in the world (like "Ireland" or "Oregon"). An Availability Zone (AZ) is a discrete, isolated data center (or cluster of them) inside that region

---

**Why does AWS have multiple regions?**

Data sovereignity, disaster recovery and putting servers close to users

---

**How many Availability Zones does each region typically have?**

The standard is 3 Availability Zones per region, though older/larger regions like us-east-1 have more.

---

**Can you deploy resources in multiple regions simultaneously?**

Yes. You can use tools like Route 53 (DNS) or S3 Cross-Region Replication to run your application across multiple regions at the same time for maximum reliability.

---

### Region Selection Analysis:

| Scenario | Best Region | Reasoning |
|----------|-------------|-----------|
| Serving users primarily in Europe | eu-central-1 (Frankfurt) or eu-west-1 (Ireland) | Reduces latency (the time it takes for data to travel) for your European users. |
| Lowest cost for non-critical workloads | [us-east-1 (N. Virginia) or us-west-2 (Oregon) | These are historically the cheapest regions because they are the oldest and largest. |
| GDPR compliance required | Any EU Region (e.g., eu-west-3 Paris) | Ensures data stays within EU borders to meet strict privacy laws. |
| Serving users in Asia-Pacific | ap-southeast-1 (Singapore) or ap-northeast-1 (Tokyo)| Best for providing a fast experience to users in the APAC region. |
| Need newest AWS services | us-east-1 (N. Virginia) | AWS almost always launches new features and services in this region first before rolling them out globally.|

---

## Bonus Challenges

### Challenge 1: Cost Estimate

**Architecture:**
- 1x t3.medium EC2 (24/7)
- 1x db.t3.micro RDS (24/7)
- 50 GB S3
- 100 GB data transfer

**Estimated Monthly Cost:** $______

**Calculator Link:** [URL]

---

### Challenge 2: Service Comparison

| AWS | Azure | GCP |
|-----|-------|-----|
| EC2 | [Azure service] | [GCP service] |
| S3 | [Azure service] | [GCP service] |
| RDS | [Azure service] | [GCP service] |
| Lambda | [Azure service] | [GCP service] |

---

### Challenge 3: CLI Advanced

[Paste outputs of advanced commands here]

---

## Reflection

**What surprised you most about AWS services?**

The amount of things a user could do with a free tier account. 

---

**Which AWS service are you most excited to learn about?**

Probably EC2 and S3 as it is used so frequently. 

---

**How comfortable do you feel navigating the AWS Console now?**

In a scale of 1 to 10, a 5. Im still in the phase of trying to get used to the interface. 

---

## Checklist

- [ ] All service dashboards visited and documented
- [ ] All CLI commands executed successfully
- [ ] All pricing research completed
- [ ] All documentation URLs found
- [ ] Region analysis completed
- [ ] All screenshots captured
- [ ] All questions answered
- [ ] Work committed to Git
- [ ] Pull request created

---

**Completed By:** France
**Date:** 21 April 2026
