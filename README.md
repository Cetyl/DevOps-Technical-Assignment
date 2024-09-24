# AWS Cost Optimization and Monitoring Project

## Overview
This project focuses on optimizing AWS costs, setting up effective monitoring and alerting systems, and improving the performance of a Next.js application hosted on AWS. The main components include cost analysis, CloudWatch monitoring, and CloudFront optimization strategies.

## Table of Contents
- [AWS Cost Optimization](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task%20-1.%20AWS%20Cost%20Optimization.md)
- [Monitoring and Alerting](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task-2.%20Monitoring%20and%20Alerting.md)
- [CloudFront Optimization for Next.js Application](https://github.com/Cetyl/DevOps-Technical-Assignment/blob/main/Task-3.%20CloudFront%20Optimization%20for%20Next.js%20Application.md)


## AWS Cost Optimization

### 1. Lambda Function Costs
- **Observation:** The Lambda service incurred a total of approximately $418.41 for the month.

#### Potential Actions:
- **Optimize Lambda Function Duration:**
  - Review the execution time of each Lambda function. Refactoring code or adjusting memory settings can reduce execution time.
  
- **Scheduled Invocation:**
  - For Lambda functions invoked on a schedule but rarely used, consider adjusting the schedule or switching to a different service.

#### Potential Savings:
- Optimizing function execution could reduce costs by up to 30%, saving around $125 per month, depending on the number of invocations and average duration.

#### Trade-offs:
- Refactoring code may require development time and resources. It’s essential to maintain efficiency without sacrificing performance.

### 2. EC2 Instances Costs
- **Observation:** The EC2 instances contributed approximately $135.57.

#### Potential Actions:
- **Right-Sizing Instances:**
  - Analyze instance utilization metrics to identify underutilized or over-provisioned instances. Downgrade or terminate consistently underused instances.
  
- **Use Spot Instances:**
  - For non-critical workloads, consider migrating to Spot Instances, which can save up to 90% compared to On-Demand pricing.

#### Potential Savings:
- Right-sizing could lead to savings of 20-40%, reducing costs by around $27-$54. Utilizing Spot Instances could yield savings of $50-$100 depending on workload requirements.

#### Trade-offs:
- Right-sizing may impact performance if not executed carefully, and Spot Instances can be interrupted, necessitating strategies to manage interruptions.

### 3. CloudWatch Costs
- **Observation:** CloudWatch expenses total approximately $73.69.

#### Potential Actions:
- **Optimize Monitoring:**
  - Review monitored metrics and logs. Disable or reduce granularity for less critical resources, or reduce log retention periods.

- **Set Alarms Wisely:**
  - Limit the number of alarms to only those necessary for critical resources.

#### Potential Savings:
- By optimizing monitoring practices, potential savings could be around 15-25%, equating to approximately $11-$18.

#### Trade-offs:
- Reducing monitoring may lead to less visibility into resource performance, potentially resulting in missed issues. Careful selection of essential metrics is crucial.

### Summary of Potential Actions
- **Lambda:** Optimize function duration and scheduling (Potential Savings: $125).
- **EC2 Instances:** Right-size instances and use Spot Instances (Potential Savings: $77-$154).
- **CloudWatch:** Optimize monitoring settings and reduce unnecessary logs/alarms (Potential Savings: $11-$18).

### Total Potential Savings
By implementing the above actions, total potential savings could range from approximately $213 to $297 monthly, significantly optimizing AWS costs while ensuring that service levels are maintained.

Regular monitoring and periodic reviews will further enhance cost efficiency and service effectiveness.

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

