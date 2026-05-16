# AWS Backup Plan for EC2 and RDS

## Objective
Configure automated backup and recovery for AWS EC2 and RDS resources using AWS Backup service.

---

## AWS Services Used
- Amazon EC2
- Amazon RDS
- AWS Backup
- Backup Vault
- Recovery Points

---

## Architecture
EC2 Instance + RDS Database → AWS Backup → Backup Vault → Recovery Points

---

## Features
- Automated daily backups
- Centralized backup management
- Recovery point creation
- Lifecycle and retention policies
- Secure backup vault configuration

---

## Infrastructure Setup

### Launch EC2 Instance
- Amazon Linux EC2 instance created
- Sample web server installed
- Test data configured

### Launch RDS Database
- MySQL database created
- Sample table and data inserted

---

## AWS Backup Configuration Steps

## Create Backup Plan

### Step 1 — Open AWS Backup
- Login to AWS Console
- Search for:
  AWS Backup

---

### Step 2 — Create Backup Vault
- Open Backup Vaults
- Click:
  Create Backup Vault

Vault Name:
```text
project2-vault
```

Purpose:
The backup vault securely stores EC2 and RDS backups.

---

### Step 3 — Create Backup Plan
- Open:
  Backup Plans
- Click:
  Create Backup Plan

Selected Option:
```text
Build a new plan
```

Backup Plan Name:
```text
project2-backup-plan
```

---

### Step 4 — Configure Backup Rule

Rule Name:
```text
daily-backup-rule
```

Backup Frequency:
```text
Daily
```

Backup Window:
```text
Default backup window
```

Retention Period:
```text
30 Days
```

Lifecycle Policy:
Configured to automatically manage backup expiration.

---

### Step 5 — Assign Resources

Resources Added:
- EC2 Instance
- RDS Database

Assignment Method:
- Resource IDs
OR
- Tags

---

### Step 6 — Start On-Demand Backup

- Open:
  Protected Resources
- Select EC2 or RDS resource
- Click:
  Create On-Demand Backup

Purpose:
To verify backup configuration and recovery point generation.

---

### Step 7 — Verify Backup Jobs

Checked:
- Backup Jobs
- Recovery Points
- Backup Vault

Result:
Backup jobs completed successfully and recovery points were created.
