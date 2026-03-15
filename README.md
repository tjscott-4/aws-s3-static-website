# AWS S3 Static Website Hosting Project

## Overview

This project demonstrates how to host a **static website using Amazon S3**.
It also shows how to configure bucket permissions and troubleshoot a **403 Access Denied** error caused by incorrect permissions.

This is one of the most common beginner cloud deployments and demonstrates real-world troubleshooting of AWS permissions.

---

## AWS Services Used

* **Amazon S3** – Object storage used to host the website
* **S3 Static Website Hosting** – Enables a bucket to serve web content
* **S3 Bucket Policies** – Controls public access to objects

---

## Project Architecture

User Browser
⬇
S3 Website Endpoint
⬇
S3 Bucket
⬇
index.html

---

## 1️⃣ Create S3 Bucket

A globally unique S3 bucket was created to store website files.

![S3 Bucket](screenshots/s3-bucket.png)

---

## 2️⃣ Upload Website Files

The `index.html` file was uploaded to the bucket to serve as the homepage.

![File Upload](screenshots/file-upload.png)

---

## 3️⃣ Enable Static Website Hosting

Static website hosting was enabled and `index.html` was configured as the **index document**.

![Static Website Hosting](screenshots/static-hosting.png)

---

## 4️⃣ Configure Public Access

Block Public Access settings were modified so the bucket could serve a public website.

![Public Access Settings](screenshots/public-access.png)

---

## 5️⃣ Configure Bucket Policy

A bucket policy was added to allow **public read access** to objects using `s3:GetObject`.

![Bucket Policy](screenshots/bucket-policy.png)

Example Policy:

```
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

## 6️⃣ Verify Website Deployment

The static website was successfully accessed using the S3 website endpoint.

![Live Website](screenshots/live-site.png)

---

## 7️⃣ Troubleshooting: 403 Access Denied

To simulate a real-world troubleshooting scenario, the bucket policy was temporarily removed.

This caused the website to return a **403 Access Denied error**.

![Access Denied](screenshots/access-denied.png)

The issue was resolved by restoring the correct bucket policy permissions.

---

## Key Skills Demonstrated

* AWS S3 configuration
* Static website hosting
* Bucket policy permissions
* Public access configuration
* Troubleshooting AWS access errors
* Cloud architecture documentation

---

## Website Endpoint

```
http://tedarrell-cloud-portfolio-2026.s3-website-us-east-1.amazonaws.com
```

---

## Author

**Tedarrell Scott Jr**

Aspiring Cloud Support / Cloud Operations Engineer
