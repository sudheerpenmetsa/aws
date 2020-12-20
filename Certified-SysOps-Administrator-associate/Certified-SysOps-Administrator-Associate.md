## Documents:
[Exam Blueprint](https://d1.awsstatic.com/training-and-certification/docs-sysops-associate/AWS%20Certified%20SysOps%20-%20Associate_Exam%20Guide_Sep18.pdf)

[Initializing Amazon EBS volumes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-initialize.html)

[Monitoring the status of your volumes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-volume-status.html)


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

## Monitoring and Reporting

### Cloud Watch
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
  
  - Pre-Warming EBS Volumes: 
    - New EBS volumes receive their maximum performance the moment that they are available and do not require initialization (formerly known as pre-warming). However, storage blocks on volumes that were restored from snapshots must be initialized(pulled down from amazon S3 and written to the volume) before you can access the block. This preliminary action takes time and can cause a significant increase in the latency of an I/O operation the first time each block is accesses. For most applications, amortizing this cost over the lifetime of the volume is acceptable. Performance is resotred after the data is accessed once.
    - You can avoid this performance hit in a production environment by reading from all of the blocks on your volume before you use it; this process is called intialization. For a new volume created from snapshot, you should read all the blocks that have data before using the volume.

    - EBS CloudWatch Metrics
   ![](EBS-CloudWatch-metrics.jpeg)

    - Volume Status Checks
   ![](volume-status-checks.jpg)   
    
    :sparkles: :sparkles: Volume Read Ops/Volume Write Ops = Total number of IO Ops in a specific period of time. So say 1000 in 1 minute = 1000/60 = IOPS

    :sparkles: :sparkles: Volume Queue Length = Number of read operations and write operation request waiting to be completed in a specific period of time.

### Monitoring ELB
  
 - 3 different types of Elastic load balancers;
      - `Application load balancer`
         Choose an Application Load Balancer when you need a flexible feature set for your web applications with HTTP and HTTPS traffic. Operating at the request level, Application Load Balancers provide advanced routing and visibility features targeted at application architectures, including microservices and containers.  
      - `Network load balancer` Choose a Network Load Balancer when you need ultra-high performance, TLS offloading at scale, centralized certificate deployment, support for UDP, and static IP addresses for your application. Operating at the connection level, Network Load Balancers are capable of handling millions of requests per second securely while maintaining ultra-low latencies.
      - `Classic load balancer`
 - 4 different ways to monitor your load balancers;
      - `CloudWatch metrics`
          - Elastic Load balanceing publishes data points to Amazon CloudWatch for your load balancers and your targets. CloudWatch enables you to retrieve statistics about those data points as an ordered set of time-series data, known as metrics. Think of a metric as a variable to monitor, and the data points as the values of that variable overtime. For example, you can monitor the total number of healthy targets for a load balancer over a specified time period. Each data point has an associated time stamp and an optional unit of measurement.
      - `Access logs` 
          - Elastic load balancing provides access logs that capture detailed information about requests sent to your load balancer. Each log containes information such as the time the request was received, the cliend IP address, latencies, request paths, and server responses. You can use these access logs to analyze traffic patterns and troubleshoot issues.
          - Access logging is an optional feature of elastic load   balacing that is disabled by default. After you enable access logging for your load balancer, elastic load balacing captures the logs and stores them in the amazon S3 bucket that you specifiy as compresses files. you can disable access logging anytime.
          - Access Logs - **SUPER IMPORTANT**
          Access logs can store data where the EC2 instance has been deleted. For example say you have a fleet of EC2 instances behind an autoscaling group. For some reason your application has a lof of 5xx error which is only reported by your end customers a couple of days after the event. If you arent storing the web server logs anwhere persistent, it is still possible to trace these 5xxx errors using access logs which would be stored on S3.
      - `Request tracing` You can use request tracing to track HTTP requests from clients to targets or other services. When the load balancer receives a request from a client, it adds or updates the X-Amzn-Trace-Id header before sending the request to the target. ANy services or applications between the load balancer and the target can also add or update this header.*Available for applications load balancer only*
  
      - `CloudTrail logs` You can use AWS CloudTrail to capture detailed information about the calls made to the elastic load balancing API and store them as log files in Amazon S3.You can use these CLoudTrail logs to determine which calls were made the source IP address where the call came from, who made the call, when the call was made, and so on.

 :sparkles: :sparkles: **CloudWatch vs CloudTrail?**
     
     - CloudWatch monitors performance
     - CloudTrail monitors API calls in the AWS platform.(in other terms used for auditing)
   