# AWS Well-Architected Framework & Cloud Adoption Framework Assessment

## TASK 2 - AWS WELL-ARCHITECTED FRAMEWORK ASSESSMENT TABLE

### Workload Description
The workload is a two-tier web application consisting of:
- Frontend hosted on a web server
- Backend relational database
- Migrating from on premises to AWS cloud infrastructure

The goal is to ensure the architecture aligns with AWS best practices across all five Well-Architected pillars.

### WAF Assessment Table

| Pillar | Observation | Improvement Recommendation | Supporting AWS Service |
|--------|-------------|---------------------------|------------------------|
| Operational Excellence | The current system lacks monitoring, logging, and automated deployment. Failures may not be detected quickly, and troubleshooting is difficult. | Implement monitoring, centralized logging, and automated deployment pipelines to improve visibility and operational control. | Amazon CloudWatch (monitoring), AWS CloudTrail (logging), AWS Systems Manager (automation), AWS CodePipeline (CI/CD) |
| Security | The existing system has limited access control and may use open firewall rules. There is no encryption or identity-based access management. | Implement least-privilege access using IAM roles, encrypt data at rest and in transit, and restrict network access using security groups. | AWS Identity and Access Management (IAM), AWS Key Management Service (KMS), Security Groups, AWS Shield |
| Reliability | The application and database run on single servers, creating a single point of failure. There is no backup or disaster recovery strategy. | Deploy application servers across multiple Availability Zones and enable automatic backups and failover for the database. | Elastic Load Balancer (ELB), Auto Scaling Groups, Amazon RDS Multi-AZ, AWS Backup |
| Performance Efficiency | The system uses fixed server capacity, which cannot adapt to changing traffic demands, leading to underutilization or performance bottlenecks. | Use Auto Scaling to dynamically adjust resources based on demand and select appropriate instance types. | Amazon EC2 Auto Scaling, Elastic Load Balancing, Amazon CloudFront |
| Cost Optimization | The system runs continuously regardless of demand, leading to unnecessary operational costs. There is no cost monitoring or optimization strategy. | Use scalable and managed services, monitor usage, and optimize resource allocation to reduce costs. | AWS Cost Explorer, AWS Trusted Advisor, Amazon EC2 Auto Scaling, Amazon RDS |

### Summary of Key Findings
The assessment identified several weaknesses in the existing architecture, including lack of monitoring, security controls, high availability, scalability, and cost optimization. However, AWS provides built-in services that address these issues effectively.

By implementing monitoring tools such as CloudWatch, security controls using IAM and encryption, reliability improvements with multi-AZ deployments, and scalability using Auto Scaling, the system can become more resilient, secure, and efficient.

These improvements align the architecture with AWS Well-Architected Framework best practices.

---

## TASK 3 – AWS CLOUD ADOPTION FRAMEWORK (CAF) READINESS SUMMARY

### 1. Business Perspective
The business perspective evaluates how cloud adoption supports organizational goals and delivers business value. Migrating the two-tier web application to AWS will enable the organization to improve scalability, reliability, and cost efficiency. Instead of relying on expensive on-premises infrastructure, AWS offers a pay-as-you-go pricing model, allowing the organization to pay only for resources consumed. This reduces capital expenditure and improves financial flexibility.

Cloud adoption also enhances business continuity by reducing downtime through high availability and automated failover mechanisms. This ensures better service delivery and improved customer satisfaction. Additionally, AWS provides global infrastructure that allows the organization to expand its services to new geographic regions more easily.

However, the organization must define clear migration objectives, including performance targets, availability requirements, and cost savings goals. Leadership support and proper budgeting are critical enablers for successful migration. The organization should also use tools such as AWS Cost Explorer to track spending and ensure financial accountability.

Overall, the organization is moderately ready but requires clear planning, budgeting, and defined business outcomes.

### 2. People Perspective
The people's perspective evaluates staff readiness, skills, and organizational culture required for cloud adoption. Currently, the organization's IT staff are experienced in managing traditional on-premises infrastructure but may lack experience with cloud technologies. Migrating to AWS requires new skills in cloud architecture, automation, monitoring, and security.

To ensure successful migration, the organization must invest in cloud training programs. Staff should be trained in AWS services such as EC2, RDS, IAM, and CloudWatch. AWS certification programs can help validate employee skills and ensure technical competence. Additionally, the organization should define new roles, such as Cloud Architect, Cloud Engineer, and Security Engineer.

The organization should also promote a cloud-first mindset that encourages automation, continuous improvement, and innovation. Proper management strategies should be implemented to help employees adapt to new tools and workflows.

With proper training and skill development, the organization can successfully manage and maintain the cloud environment.

### 3. Governance Perspective
The governance perspective ensures that cloud adoption aligns with organizational policies, compliance requirements, and risk management strategies. Currently, the organization may lack defined governance policies for cloud resource management, cost control, and security compliance.

To improve governance readiness, the organization should implement clear policies for resource provisioning, access control, and cost management. AWS Identity and Access Management (IAM) should be used to control user permissions based on the principle of least privilege. Resource tagging should be implemented to track usage and allocate costs properly.

Cost management tools such as AWS Budgets and AWS Cost Explorer should be used to monitor and control spending. Additionally, AWS Config can be used to monitor compliance and ensure resources meet security standards.

Infrastructure should be managed using Infrastructure as Code (IaC), such as AWS CloudFormation, to ensure consistency and reduce configuration errors.

These governance improvements will ensure secure, compliant, and controlled cloud operations.

### 4. Platform Perspective
The platform perspective focuses on the technical infrastructure required to support cloud workloads. AWS provides a reliable and scalable platform that improves system availability and performance.

The organization should deploy its web application using Amazon EC2 instances within Amazon Virtual Private Cloud (VPC). Public subnets should host load balancers, while private subnets should host application servers and databases for improved security. Amazon RDS should be used as a managed database service with multi-AZ deployment for high availability.

Elastic Load Balancing should distribute traffic across multiple EC2 instances, while Auto Scaling should automatically adjust resources based on demand. Amazon S3 should be used for storing static content and backups.

This platform design improves scalability, availability, security, and performance while reducing operational overhead.

The organization is technically ready but must implement proper architecture design and automation.

### 5. Security Perspective
The security perspective ensures that cloud workloads are protected from unauthorized access and threats. Currently, the organization may rely on basic security controls used in on-premises environments.

AWS provides advanced security features such as IAM for access control, encryption using AWS Key Management Service (KMS), and monitoring using AWS CloudTrail. These tools help protect sensitive data and ensure accountability.

The organization should implement least-privilege access policies, ensuring users only access resources necessary for their roles. Security groups should restrict network traffic, and data should be encrypted both at rest and in transit.

Monitoring tools such as Amazon CloudWatch should be used to detect suspicious activity and system failures.

These improvements will significantly enhance the organization's security posture and protect its applications and data.

### 6. Operations Perspective
The operations perspective focuses on managing, monitoring, and maintaining cloud workloads efficiently. Currently, the organization relies heavily on manual processes, which increases the risk of errors and downtime.

AWS provides tools such as Amazon CloudWatch for monitoring system performance and AWS Systems Manager for managing infrastructure. These tools enable automated monitoring, alerting, and maintenance.

The organization should implement automated backups using AWS Backup and enable multi-AZ deployment for disaster recovery. Automated deployment pipelines using CI/CD tools such as AWS CodePipeline will improve deployment speed and reliability.

Operational procedures should be documented clearly to ensure consistency and efficiency.

By implementing automation, monitoring, and backup solutions, the organization will improve operational efficiency and system reliability.

---

## REFLECTION

This lab helped me understand how to evaluate and design cloud architecture using AWS best practices. By applying the AWS Well-Architected Framework, I learned how to analyze a system across five key pillars: Operational Excellence, Security, Reliability, Performance Efficiency, and Cost Optimization. This process helped me identify weaknesses such as single points of failure, lack of monitoring, and poor security controls. I also learned how AWS services like Auto Scaling, Load Balancers, and Amazon RDS improve system availability, scalability, and reliability.

Using the AWS Cloud Adoption Framework helped me understand that successful cloud migration is not only about technology but also involves business planning, governance, security, operations, and people readiness. I learned the importance of training staff, defining policies, and implementing proper monitoring and automation.

Overall, this lab improved my ability to think like a cloud architect by evaluating risks, recommending improvements, and designing scalable, secure, and cost-effective cloud solutions aligned with AWS best practices.
