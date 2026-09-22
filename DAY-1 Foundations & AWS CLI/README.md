# AWS Day 1

## 🎯 What I Learned

### 1. AWS & Cloud Computing

AWS provides on-demand cloud services such as compute, storage, networking, databases, and monitoring.

Cloud resources can be managed through the AWS Console, CLI, and APIs/SDKs.

### 2. AWS Global Infrastructure

```text
AWS
├── Regions
├── Availability Zones
└── Edge Locations
```

**Region** → Geographic AWS area containing multiple Availability Zones.

**Availability Zone (AZ)** → Isolated infrastructure location within a Region.

**Edge Location** → Used by services such as CloudFront to deliver cached content closer to users.

### 3. Region Awareness

AWS resources can be Region-specific.

Example:

```text
EC2 created in Mumbai
        ↓
Switch Console to Singapore
        ↓
EC2 may not appear
```

**Troubleshooting habit:** Check the selected Region before assuming a resource was deleted.

### 4. AWS Account & Resources

```text
AWS Account
├── EC2
├── S3
├── VPC
├── IAM
└── CloudWatch
```

**Service** → AWS capability, e.g. EC2.

**Resource** → Specific object created using the service, e.g. an EC2 instance.

### 5. AWS CLI

AWS CLI allows AWS services to be managed from the terminal.

Basic structure:

```bash
aws <service> <operation> [options]
```

Example:

```bash
aws s3 ls
```

Meaning:

```text
aws → AWS CLI
s3  → S3 service
ls  → list
```

### 6. Hands-on

Verified AWS CLI installation:

```bash
aws --version
```

Also explored:

```bash
aws help
```

### 7. CLI Authentication

Tested AWS authentication with:

```bash
aws sts get-caller-identity
```

Encountered:

```text
InvalidClientTokenId
```

**Lesson:** Credentials being configured locally does not necessarily mean they are valid. Authentication problems can involve invalid, inactive, mismatched, or overridden credentials.

## 🧠 Key Takeaways

* AWS Region and AZ are different concepts.
* Region selection matters when working with regional resources.
* Console and CLI are different ways to interact with AWS APIs.
* AWS CLI commands follow a structured pattern.
* Always verify the Region and credentials when troubleshooting.
