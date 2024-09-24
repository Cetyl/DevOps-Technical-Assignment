# AWS Cost Optimization and Monitoring Project

## Overview
This project focuses on optimizing AWS costs, setting up effective monitoring and alerting systems, and improving the performance of a Next.js application hosted on AWS. The main components include cost analysis, CloudWatch monitoring, and CloudFront optimization strategies.

## Table of Contents
- [AWS Cost Optimization](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task%20-1.%20AWS%20Cost%20Optimization.md)
- [Monitoring and Alerting](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task-2.%20Monitoring%20and%20Alerting.md)
- [CloudFront Optimization for Next.js Application](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task-3.%20CloudFront%20Optimization%20for%20Next.js%20Application.md)


## AWS Cost Optimization

### 1. Lambda Function Costs
- **Cost:** ~$418.41/month.
- **Actions:** Optimize execution and adjust schedules.
- **Savings:** Up to $125/month (30%).

### 2. EC2 Instances Costs
- **Cost:** ~$135.57/month.
- **Actions:** Right-size instances and use Spot Instances.
- **Savings:** $27-$154/month.

### 3. CloudWatch Costs
- **Cost:** ~$73.69/month.
- **Actions:** Reduce monitored metrics and alarms.
- **Savings:** $11-$18/month.

### Total Potential Savings
**Approximately $213 to $297/month** through optimization efforts.


## Monitoring and Alerting
### CloudWatch Dashboard Design
The dashboard provides visibility into key metrics for EC2 instances, Lambda functions, and S3 buckets.

### Key CloudWatch Alarms
1. **High CPU Usage on EC2:**
   - **Threshold:** Set at 80%.
   - **Action:** Notify via AWS SNS when the threshold is breached.

2. **Lambda Function Errors:**
   - **Threshold:** More than 5 errors within a minute.
   - **Action:** Notify via AWS SNS for immediate attention.

### Notifications Setup
AWS Simple Notification Service (SNS) is configured to send alerts via email or SMS whenever an alarm is triggered.

## CloudFront Optimization for Next.js Application
### a) High Availability
- **Strategy:** Implement a multi-origin setup with CloudFront to ensure high availability.
- **Testing:** Conduct failover simulations by temporarily disabling one origin.

### b) Bot Attack Mitigation
- **Methods:** Utilize AWS WAF to establish rate limiting rules.
- **Benefits:** Mitigates DDoS attacks and promotes fair usage among users.

### c) SEO Crawler Allowance
- **Implementation:** Use User-Agent strings to differentiate and allow legitimate SEO crawlers while blocking malicious bots.
- **Configuration:** Establish WAF rules based on User-Agent and IP address lists.

### d) Monitoring
- **Key Metrics:** Track cache hit ratios, request counts, and error rates.
- **Logging Setup:** Enable CloudFront logging for detailed performance insights.

### e) Site Loading Time Optimization
1. **Enable Gzip Compression:** Compress data to reduce transfer size.
2. **Use Caching:** Set appropriate cache headers for static assets.
3. **Optimize Images:** Deliver images in modern formats like WebP for efficiency.

**Impact Measurement:** Monitor load times using CloudWatch metrics before and after optimizations to assess effectiveness.

## Conclusion
This project provides a comprehensive approach to managing AWS costs, establishing effective monitoring, and enhancing performance for a Next.js application. Implementing these strategies can significantly improve both resource efficiency and application performance.

