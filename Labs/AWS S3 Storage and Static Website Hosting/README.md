# AWS S3 Storage and Static Website Hosting

## Objective

Create and configure an Amazon S3 bucket, upload and manage objects, understand access control mechanisms using ACLs and Bucket Policies, and host a static website using Amazon S3 Static Website Hosting.

---

## Services and Technologies Used

### AWS Services

* Amazon S3

### Storage

* Object Storage

### Access Management

* Access Control Lists (ACLs)
* Bucket Policies

### Web Technologies

* HTML
* Static Website Hosting

---

## Architecture Diagram

```text
                     User Browser
                           |
                           |
                     HTTP Request
                           |
                           |
                  +------------------+
                  | Amazon S3 Bucket |
                  |   index.html     |
                  +------------------+
                           |
                           |
                  Static Website
                       Hosting
```

### Architecture Description

* An Amazon S3 bucket was created for object storage.
* Files were uploaded and managed within the bucket.
* Access permissions were configured using ACLs and Bucket Policies.
* Static Website Hosting was enabled on the bucket.
* HTML files were served directly from Amazon S3.
* The hosted website was accessed through the S3 Website Endpoint.

---

## Project Overview

This project demonstrates the use of Amazon S3 as a scalable object storage service. Objects were uploaded to a bucket, access permissions were configured, and a static website was hosted using Amazon S3 Static Website Hosting. The project also provided practical experience with S3 access control and website deployment.

---

## Implementation

### 1. S3 Bucket Creation

An Amazon S3 bucket was created to store and manage objects.

#### Activities Performed

* Opened the Amazon S3 Console.
* Created a new S3 bucket.
* Configured bucket settings.
* Reviewed Object Ownership options.
* Configured public access settings.

#### Outcome

* Successfully created an Amazon S3 bucket for object storage.

---

### 2. Object Upload and Storage

Files were uploaded to the created S3 bucket.

#### Activities Performed

* Uploaded files and folders to the bucket.
* Generated Object URLs.
* Attempted direct browser access to uploaded objects.

#### Outcome

* Objects were successfully stored in Amazon S3.

---

### 3. Understanding Access Control

Initially, uploaded objects were not publicly accessible.

#### Activities Performed

* Accessed the Object URL through a browser.
* Observed an "Access Denied" error.
* Identified that S3 objects are private by default.

#### Outcome

* Understood the default security behavior of Amazon S3.

---

### 4. Access Control Using ACLs

Object permissions were modified using Access Control Lists (ACLs).

#### Activities Performed

* Configured public read access for uploaded objects.
* Enabled access for Everyone (public access).
* Verified successful object accessibility.

#### Outcome

* Uploaded objects became publicly accessible through their Object URLs.

---

### 5. Bucket Policies

Bucket-level permissions were configured using Bucket Policies.

#### Activities Performed

* Created and applied a Bucket Policy.
* Configured access permissions for bucket resources.
* Verified policy-based access control.

#### Outcome

* Successfully managed access permissions using Bucket Policies.

---

### 6. Static Website Hosting

Amazon S3 Static Website Hosting was used to host a simple website.

#### Activities Performed

* Created an HTML webpage.
* Uploaded website files to an S3 bucket.
* Enabled Static Website Hosting.
* Configured index and error documents.
* Accessed the generated Website Endpoint.

#### Outcome

* Successfully hosted and accessed a static website using Amazon S3.

---

## Key Learnings

* Amazon S3 Object Storage
* Bucket Creation and Configuration
* Object Upload and Management
* Public vs Private Access
* Access Control Lists (ACLs)
* Bucket Policies
* Static Website Hosting
* Website Endpoint Configuration
* Cloud Storage Management

---

## Skills Demonstrated

* Amazon S3
* Cloud Storage Administration
* Object Storage Management
* Access Control Configuration
* Bucket Policy Management
* Static Website Hosting
* HTML Deployment
* AWS Cloud Services

---

## Conclusion

Successfully created and configured Amazon S3 buckets for object storage and static website hosting. The project demonstrated object management, access control using ACLs and Bucket Policies, and deployment of a publicly accessible static website through Amazon S3. This hands-on exercise provided practical experience with cloud storage services and web hosting using AWS.

