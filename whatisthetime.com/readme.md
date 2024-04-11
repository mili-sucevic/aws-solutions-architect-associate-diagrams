# AWS Architectural Solution - whatisthetime.com

## Overview:
This document provides an architectural overview and setup guide for the deployment of whatsthetime.com on Amazon Web Services (AWS). The solution involves utilising AWS services like Elastic Load Balancer (ELB), Route 53 for DNS management, EC2 instances in multiple availability zones (AZs), Auto Scaling Groups, and reserved instances for cost optimisation.

## Architecture Diagram:
![whatisthetime-diagram(1)](https://github.com/mili-sucevic/aws-solutions-architect-associate-diagrams/assets/93227818/bbce15c5-0410-4afd-9876-b867bdc87c53)

### Components and Setup:
**1. DNS Configuration using Route 53:**

**Description:** Using Route 53, a globally accessible DNS service, helps to quickly and accurately direct users to the whatsthetime.com platform. By configuring alias records, the system ensures efficient resolution of domain names, directing traffic to the right endpoints. Additionally, Route 53 offers a range of advanced features like health checks, traffic policies, and latency-based routing. These features enhance the platform's performance and availability. With these tools, the whatsthetime.com platform can offer its customers an exceptional user experience, regardless of their location or network conditions.
- Create a hosted zone for whatsthetime.com in Route 53.
- Add an alias record (API) pointing to the ELB's DNS name.

**2. ELB Setup:**
   
**Description:** The system's infrastructure is built around the Elastic Load Balancer, which directs incoming traffic to different instances. This helps improve the system's efficiency by making sure that resources are used effectively. The Elastic Load Balancer also helps prevent downtime by redirecting requests to other available instances if one of them fails. This ensures that users can continue to use the system without interruption.
- Create an Application Load Balancer or Network Load Balancer based on your requirements.
- Configure listeners, target groups, and health checks as needed.

**3. Multi-AZ EC2 Instances with Auto Scaling:**

**Description:** The deployment encompasses Amazon EC2 instances distributed across multiple Availability Zones (AZs) to mitigate the risk of downtime and enhance resilience against regional outages. These instances are intelligently managed through Auto Scaling Groups, dynamically scaling in response to fluctuating demand while maintaining a predefined minimum capacity for consistent performance.
- Launch EC2 instances in multiple AZs, ensuring they are part of the same VPC as the ELB.
- Configure security groups to allow necessary inbound traffic.
- Install and configure the required software on the instances.

**4. Reserved Instances for Cost Optimisation:** 

**Description:** Employing Reserved Instances (RI), the architecture strategically aligns with cost optimisation objectives. By committing to reserved capacity at discounted rates, the platform ensures long-term predictability in expenditure while maximizing ROI. The reserved instances are meticulously aligned with Auto Scaling Groups, optimizing cost savings without compromising operational efficiency
- Identify the instance types and AZs used in the Auto Scaling Group.
- Purchase reserved instances matching the specifications for maximum cost savings.
- Ensure the number of reserved instances matches the minimum capacity of the Auto Scaling Group.

### Testing and Monitoring:
- Test the functionality of whatsthetime.com to ensure proper operation.
- Monitor the performance and health of EC2 instances, ELB, and Auto Scaling Group using AWS CloudWatch.
- Set up alarms and notifications for critical metrics to promptly address any issues.

### Conclusion:
Whatsthetime.com is a website hosted on AWS that provides users with a seamless and reliable experience. This is made possible by using AWS services like Route 53 for domain name system management, Elastic Load Balancing to distribute incoming traffic, and EC2 Auto Scaling for automatic scaling of web server capacity. Additionally, Reserved Instances are used for cost optimization. This makes whatsthetime.com scalable, resilient, and cost-effective.
