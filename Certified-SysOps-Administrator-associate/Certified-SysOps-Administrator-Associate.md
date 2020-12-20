## Documents:
[Exam Blueprint](https://d1.awsstatic.com/training-and-certification/docs-sysops-associate/AWS%20Certified%20SysOps%20-%20Associate_Exam%20Guide_Sep18.pdf)


| Objective | % of Examination | 
| -------- | -------- | 
|Domain 1: Monitoring and Reporting |22% |
|Domain 2: High Availability |8% |
|Domain 3: Deployment and Provisioning  | 14%|
|Domain 4: Storage and Data Management  |12% |
|Domain 5: Security and Compliance |18% |
|Domain 6: Networking  |14% |
|Domain 7: Automation and Optimization |12% |
|**TOTAL**  |**100%** |

## Cloud Watch
- A cloud watch is a monitroing service to monitor AWS resources,as well as well as applications that run on AWS.

- CloudWatch can monitor things like:
  - Compute
     - Autoscaling groups
     - Elastic Load Balancers
     - Route53 Health Checks
  - Storage and Content Delivery
     - EBS Volumes
     - Storage Gateways
     - CloudFront
  - Databases and Analytics
     - DynamoDB
     - Elasticache Nodes
     - RDS Instances
     - Elastic MapReduce Job Flows
     - Redshift      

  - Other
     - SNS(Simple Notification Service) Topics
     - SQS(Simple Queue Service) Queues
     - Opsworks
     - CloudWatch Logs
     - Estimated charges on your AWS Bill 

  - Host Level Metrics always consists of:
     - CPU
     - Network
     - Disk
     - Status Check


  :sparkles: :sparkles: RAM utilization 
  It is a custom metric! By default EC2 monitoring is 5 minute intervals, unless you enable detailed monitoring which will then make it 1 minute intervals.

  :sparkles: :sparkles: Metric Granularity
   - 1 minute for detailed monitoring
   - 5 minutes for standard monitoring
  
  :sparkles: :sparkles: CloudWatch can be used on premise - Not restricted to just AWS resources. Can be on premise too. Just need to download and install the SSM agent and Cloudwatch agent.

  ### Monitoring EBS
  - EBS Different types of EBS storage;
     - General purpose (SSD) - gp2
     - Provisioned IOPS (SSD) - io1
     - Throughput Optimized (HDD) - st1
     - Cold (HDD) - sc1

![compare volumetypes](volumetypes.jpg)