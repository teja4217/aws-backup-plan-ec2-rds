# AWS Backup Plan for EC2 and RDS

## Objective
Configure automated backup and recovery for AWS EC2 and RDS resources using AWS Backup service.

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Amazon EC2 | Virtual server used for testing backup configuration |
| Amazon RDS | Managed relational database service used for database backup |
| AWS Backup | Centralized backup management service |
| Backup Vault | Secure storage location for recovery points |
| Recovery Points | Restore points created from backups |
| IAM Role | Permissions for AWS Backup operations |
| Linux | Operating system used on EC2 instance |
| MySQL | Database engine used in RDS |
| AWS Management Console | Used to configure and monitor backup services |

---

### AWS Services Implemented
- EC2
- RDS
- AWS Backup
- IAM
- Backup Vault

---

### Key Cloud Concepts Used
- Automated Backup Scheduling
- Disaster Recovery
- Recovery Point Management
- Retention Policy Configuration
- Backup Lifecycle Management


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

After creating the backup plan, AWS resources were assigned to the backup policy.

---

#### Resources Selected
- Amazon EC2 Instance
- Amazon RDS MySQL Database

---

#### Assignment Method

AWS Backup supports:
- Resource ID assignment
- Tag-based assignment

For this project, resources were assigned directly using Resource IDs.

---

#### Steps Performed

1. Open AWS Backup Console
2. Navigate to:
   Backup Plans
3. Select:
   project2-backup-plan
4. Click:
   Assign Resources
5. Enter Assignment Name:

```text
project2-resource-assignment
```

6. Select IAM Role:
```text
Default AWS Backup Role
```

7. Choose Resource Type:
- EC2
- RDS

8. Select created EC2 and RDS resources

9. Click:
```text
Assign Resources
```

---

#### Purpose of Resource Assignment

Resource assignment connects AWS resources to the backup plan so backups can run automatically based on configured schedules.

---

#### Result

- EC2 instance successfully added to backup plan
- RDS database successfully added to backup plan
- Automated backup scheduling enabled


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
- ## Validation & Testing

### Step 1 — Trigger On-Demand Backup

To verify the backup configuration, an on-demand backup was manually triggered.

Steps performed:
1. Open AWS Backup Console
2. Navigate to:
   Protected Resources
3. Select:
   EC2 Instance or RDS Database
4. Click:
   Create On-Demand Backup
5. Select Backup Vault:
```text
project2-vault
```
6. Start Backup Job

---

### Step 2 — Monitor Backup Jobs

Backup job status was verified under:

```text
AWS Backup → Backup Jobs
```

Observed Status:
```text
Completed Successfully
```

Both:
- EC2 backup
- RDS backup

were completed successfully.

---

### Step 3 — Verify Recovery Points

Recovery points were validated under:

```text
AWS Backup → Backup Vault → Recovery Points
```

Verified Items:
- EC2 recovery point
- RDS recovery point
- Backup timestamps
- Backup size and status

---

### Step 4 — Validation Result

The following validations were completed successfully:
- Automated backup scheduling
- EC2 backup creation
- RDS backup creation
- Recovery point generation
- Backup vault storage verification

---

## Project Outcome

Successfully implemented an automated AWS Backup solution for Amazon EC2 and Amazon RDS resources using AWS Backup service.

The project achieved the following:

- Configured centralized backup management using AWS Backup
- Created secure Backup Vault for storing recovery points
- Implemented automated daily backup scheduling
- Configured lifecycle and retention policies
- Assigned EC2 and RDS resources to backup plans
- Triggered and validated on-demand backups
- Verified successful recovery point generation
- Improved disaster recovery and data protection capabilities

---

### Skills Demonstrated
- AWS Backup Administration
- EC2 Management
- RDS Database Management
- Cloud Disaster Recovery
- Backup Lifecycle Management
- AWS Resource Assignment
- Monitoring and Validation

---

### Final Result

The backup system successfully protected AWS infrastructure resources and ensured reliable recovery capabilities for both EC2 and RDS services.

## Project Screenshots

### RDS Database
![RDS](screenshots/picture2.png)

### Backup Plan
![Backup Plan](screenshots/picture9.png)

### Recovery Points
![Recovery Points](screenshots/picture11.png)

### vault
![vault](screenshots/picture10.png)

Result:
Backup jobs completed successfully and recovery points were created.
