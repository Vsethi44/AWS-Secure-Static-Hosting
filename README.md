# AWS-Secure-Static-Hosting
A comprehensive solution for hosting a secure, reliable, and efficient static web page using AWS services

## Introduction
The project aims to develop a secure, reliable, and efficient hosting solution for a static web page. The organization's current infrastructure lacks essential security measures, redundancy, and global accessibility, leading to potential security breaches, downtime, and slow website performance. This project provides a comprehensive solution using Amazon Web Services (AWS) to address these concerns.

## Problem Statement
An organization requires a solution for hosting a static web page that ensures firewall protection, failover capabilities, geographical restrictions, and low latency access. The existing infrastructure's shortcomings include inadequate security, lack of redundancy, and poor global accessibility, resulting in potential security breaches, downtime, and slow website performance. The organization needs a hosting solution with robust firewall protection, automatic failover mechanisms, geographical access restrictions, and low latency access for users worldwide.

## Goal
To provide a hosting solution that ensures secure, reliable, and efficient global access to the organization's web page.

## Resources Used
- **Amazon S3**: To host the static website.
- **Amazon CloudFront Distribution**: To provide an automatic failover mechanism, enforce geographical restrictions, and ensure low latency access.
- **Amazon WAF (Web Application Firewall)**: For firewall protection.

## Tasks Performed

### Task 1: Created Two S3 Buckets
**Objective**: Set up primary and secondary buckets to host the static website.

**Steps Followed**:
1. Created the primary bucket: `Vishawnathbucket1`
2. Created the secondary bucket: `Vishawnathbucket2`
3. Created an `index.html` file and uploaded it to both primary and secondary buckets.

### Task 2: Created CloudFront Distribution
**Objective**: Set up CloudFront to distribute and serve content from the S3 buckets with enhanced features.

**Steps Followed**:
1. Created a CloudFront distribution.
2. Selected the primary bucket for the origin domain.
3. Created a new origin access identity (OAI).
4. Modified settings in the "Default behavior" to disable caching.

### Task 3: Configured CloudFront for Failover
**Objective**: Ensure high availability by configuring failover between the primary and secondary S3 buckets.

**Steps Followed**:
1. Added the secondary bucket as an origin in the distribution.
2. Selected the previously created OAI for origin access.
3. Created an origin group.
4. Configured failover criteria to include all 4xx errors.
5. Edited the behavior settings to use the newly created origin group.

### Task 4: Tested Failover
**Objective**: Validate the failover mechanism works as expected when the primary bucket is unavailable.

**Steps Followed**:
1. Accessed the website using the CloudFront origin domain URL.
2. Deleted the `index.html` file from the primary S3 bucket.
3. Confirmed the website was still accessible, fetching `index.html` from the secondary bucket.

### Task 5: Added WAF to CloudFront
**Objective**: Implement firewall protection to filter and allow/deny traffic based on predefined rules.

**Steps Followed**:
1. Enabled the web application firewall (WAF) in the CloudFront distribution's security settings.

### Task 6: Implemented Geo-Location Restrictions
**Objective**: Restrict access to the website based on geographic location.

**Steps Followed**:
1. Edited the geographic restriction settings in the CloudFront distribution's security tab.
2. Attempted to access the website from a blocked location and confirmed access was denied.

### Task 7: Invalidated Data in Cache
**Objective**: Ensure updated content is served by invalidating cached data in CloudFront.

**Steps Followed**:
1. Invalidated the `index.html` file, removing it from edge locations to ensure updated content is served.

### Task 8: Deleted Resources
**Objective**: Clean up and delete all resources created in AWS.

**Steps Followed**:
1. Disabled and deleted the CloudFront distribution.
2. Deleted the primary and secondary S3 buckets.

## Conclusion
This project successfully provided a secure, reliable, and efficient global hosting solution for the organization's static web page. By leveraging AWS services such as S3, CloudFront, and WAF, the project achieved robust firewall protection, automatic failover capabilities, geographical restrictions, and low latency access.

## Contact
For further information or support, please contact [vishawnath.sethi786@hotmail.com]
