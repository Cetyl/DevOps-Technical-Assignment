# AWS Cost Optimization Analysis

August Cost - https://drive.google.com/file/d/1INmpJ3PlFVr8nKzxbz_nkW0guqsvGONR/view?usp=sharing

Based on the provided AWS Cost Explorer report, here are three potential areas for cost reduction, along with proposed actions and their implications:

## 1. Lambda Function Costs
- **Observation**: The Lambda service incurred a total of approximately **$418.41** for the month.

### Potential Actions:
- **Optimize Lambda Function Duration**: 
  - Review the execution time of each Lambda function. If functions are running longer than necessary, refactoring or editing the code or adjusting memory settings could reduce execution time.
  
- **Scheduled Invocation**: 
  - If any Lambda functions are invoked on a schedule but not used regularly, consider adjusting the schedule or switching to a different service.

### Potential Savings:
- Optimizing function execution could reduce costs by up to **30%**, potentially saving around **$125** per month, depending on the number of invocations and average duration.

### Trade-offs:
- Refactoring code may require development time and resources. Ensuring functions remain efficient without sacrificing performance is essential.

---

## 2. EC2 Instances Costs
- **Observation**: The EC2 instances contributed approximately **$135.57**.

### Potential Actions:
- **Right-Sizing Instances**: 
  - Analyze instance utilization metrics to identify underutilized or over-provisioned instances. Downgrade or terminate instances that are consistently underused.
  
- **Use Spot Instances**: 
  - For non-critical workloads, consider migrating to Spot Instances, which can save up to **90%** compared to On-Demand pricing.

### Potential Savings:
- Right-sizing could lead to savings of **20-40%**, potentially reducing costs by around **$27-$54**. Utilizing Spot Instances could yield savings in the range of **$50-$100** depending on workload requirements.

### Trade-offs:
- Right-sizing may impact performance if not done carefully, and Spot Instances can be interrupted, requiring strategies to manage interruptions effectively.

---

## 3. CloudWatch Costs
- **Observation**: CloudWatch expenses total approximately **$73.69**.

### Potential Actions:
- **Optimize Monitoring**: 
  - Review metrics and logs being monitored. Disable or reduce the granularity of monitoring for less critical resources or reduce the retention period for logs.
  
- **Set Alarms Wisely**: 
  - Limit the number of alarms set up to only those necessary for critical resources.

### Potential Savings:
- By optimizing monitoring practices, savings could be around **15-25%**, equating to approximately **$11-$18**.

### Trade-offs:
- Reducing monitoring may result in less visibility into resource performance, potentially leading to missed issues. Careful consideration of which metrics are essential is important.

---

## Summary of Potential Actions
- **Lambda**: Optimize function duration and scheduling (Potential Savings: **$125**).
- **EC2 Instances**: Right-size instances and use Spot Instances (Potential Savings: **$77-$154**).
- **CloudWatch**: Optimize monitoring settings and reduce unnecessary logs/alarms (Potential Savings: **$11-$18**).

## Total Potential Savings
By implementing the above actions, total potential savings could range from approximately **$213 to $297** monthly, significantly optimizing AWS costs while ensuring that service levels are maintained.

Regular monitoring and periodic reviews will further enhance cost efficiency and service effectiveness.
