# AWS S3 Static Website Hosting Project

## Overview

This project demonstrates how to host a static website using **Amazon S3 Static Website Hosting**.  
It also includes troubleshooting a common **403 Access Denied** error caused by incorrect bucket permissions.

This project shows basic AWS cloud skills including S3 configuration, bucket policies, and troubleshooting.

---

## AWS Services Used

- Amazon S3
- S3 Static Website Hosting
- S3 Bucket Policies

---

## Project Architecture

User Browser → S3 Website Endpoint → S3 Bucket → index.html

---

## 1. Create S3 Bucket

A globally unique S3 bucket was created to store website files.

![S3 Bucket and File Upload](screenshots/01-s3-bucket-and-file-upload.png)

---

## 2. Enable Static Website Hosting

Static website hosting was enabled and `index.html` was configured as the index document.

![Static Website Hosting](screenshots/02-static-website-hosting-enabled.png)

---

## 3. Configure Public Access

Block Public Access settings were modified to allow the bucket to host a public website.

![Public Access Settings](screenshots/03-public-access-settings.png)

---

## 4. Configure Bucket Policy

A bucket policy was added to allow public read access to website files.

![Bucket Policy](screenshots/04-bucket-policy-public-read.png)

Example policy:

```json
{
 "Version":"2012-10-17",
 "Statement":[
   {
     "Sid":"PublicReadGetObject",
     "Effect":"Allow",
     "Principal":"*",
     "Action":"s3:GetObject",
     "Resource":"arn:aws:s3:::tedarrell-cloud-portfolio-2026/*"
   }
 ]
}
```

---

## 5. Verify Website Deployment

The static website was successfully accessed using the S3 website endpoint.

![Live Website](screenshots/05-live-website.png)

---

## 6. Troubleshooting: 403 Access Denied

To simulate a real-world troubleshooting scenario, the bucket policy was removed.  
This caused the website to return a **403 Access Denied** error.

![Access Denied Error](screenshots/06-access-denied-error.png)

---

## 7. Restore Website Access

The issue was resolved by restoring the correct bucket policy.

![Site Restored](screenshots/07-site-restored.png)

---

## Key Skills Demonstrated

- AWS S3 configuration
- Static website hosting
- Bucket policy permissions
- Public access configuration
- Troubleshooting AWS access errors

---

## Website Endpoint

```
http://tedarrell-cloud-portfolio-2026.s3-website-us-east-1.amazonaws.com
```

---

## Author

**Tedarrell Scott Jr**

Aspiring Cloud Support / Cloud Operations Engineer
