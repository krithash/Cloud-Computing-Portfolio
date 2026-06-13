# AWS EBS Volume Management

## Objective

Create and attach an Amazon Elastic Block Store (EBS) volume to a Windows EC2 instance, initialize and format the volume using Windows Disk Management, and make the additional storage available for use.

---

## Services and Technologies Used

### AWS Services

* Amazon EC2
* Amazon Elastic Block Store (EBS)

### Operating System

* Windows Server on Amazon EC2

### Storage Configuration

* General Purpose SSD (gp3)
* 10 GiB Storage Capacity

### File System

* NTFS

---

## Architecture Diagram

```text
                    AWS Cloud
                         |
                         |
                +----------------+
                | Windows EC2    |
                | Instance       |
                +----------------+
                         |
                         |
                  Attached Volume
                         |
                         |
                +----------------+
                | Amazon EBS     |
                | gp3 Volume     |
                | 10 GiB         |
                +----------------+
                         |
                         |
                 NTFS File System
                         |
                         |
                    D:\ Drive
```

### Architecture Description

* A Windows EC2 instance was deployed within AWS.
* An Amazon EBS gp3 volume was created and attached to the running Windows EC2 instance.
* Windows Disk Management was used to initialize and format the newly attached storage volume.
* The volume was assigned a drive letter and made available for storage operations.
* The additional storage was successfully verified through Windows File Explorer.

---

## Project Overview

This project demonstrates the provisioning and attachment of Amazon EBS storage to a Windows EC2 instance. The EBS volume was created, attached to the instance, initialized through Windows Disk Management, formatted using the NTFS file system, and verified for use as additional storage.

---

## Configuration Used

| Parameter         | Value                |
| ----------------- | -------------------- |
| Volume Type       | gp3                  |
| Volume Size       | 10 GiB               |
| Availability Zone | ap-south-1a          |
| Target Instance   | Windows EC2 Instance |
| Device Name       | xvdf                 |
| File System       | NTFS                 |

---

## Implementation

### 1. EBS Volume Creation

A new Amazon EBS volume was created from the AWS EC2 console.

#### Activities Performed

* Opened the EC2 Dashboard.
* Navigated to Volumes.
* Created a new EBS volume.
* Selected gp3 as the volume type.
* Configured a storage capacity of 10 GiB.
* Selected the same Availability Zone as the target Windows EC2 instance.

#### Outcome

* Successfully provisioned an Amazon EBS volume.

---

### 2. Volume Attachment to EC2 Instance

The created EBS volume was attached to the Windows EC2 instance.

#### Activities Performed

* Selected the newly created EBS volume.
* Chose the target Windows EC2 instance.
* Assigned the device name xvdf.
* Attached the volume successfully.

#### Outcome

* The EBS volume became available to the Windows operating system.

---

### 3. Disk Initialization and Formatting

The attached EBS volume appeared as an unallocated disk within Windows Disk Management.

#### Activities Performed

* Opened Disk Management.
* Located the newly attached unallocated disk.
* Created a New Simple Volume.
* Assigned a drive letter.
* Formatted the partition using the NTFS file system.
* Enabled Quick Format.

#### Outcome

* The EBS volume was successfully initialized and prepared for storage operations.

---

### 4. Volume Verification

The newly configured storage volume was verified through Windows File Explorer.

#### Activities Performed

* Opened This PC.
* Verified the newly assigned drive.
* Confirmed successful storage accessibility.

#### Outcome

* Additional storage was successfully mounted and ready for use.

---

## Key Learnings

* Amazon EBS volume provisioning
* Block-level storage concepts in AWS
* Volume attachment to EC2 instances
* Windows Disk Management
* Disk initialization and partitioning
* NTFS file system formatting
* Cloud storage administration

---

## Skills Demonstrated

* AWS EC2
* Amazon EBS
* Windows Server Administration
* Storage Management
* Disk Partitioning
* Volume Configuration
* Cloud Infrastructure Administration

---

## Conclusion

Successfully created and attached an Amazon EBS volume to a Windows EC2 instance. The volume was initialized, formatted using the NTFS file system, assigned a drive letter, and verified for use. This project provided practical experience in AWS block storage management and demonstrated how additional persistent storage can be integrated with cloud-based virtual machines.
