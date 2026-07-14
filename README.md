# Hi, I'm Valen!

Cloud and DevOps Engineer.

- AWS Certified Cloud Practitioner · GCP Associate Cloud Engineer 
- Currently at Apple DevOps Institute, graduating November 2026 
- B.Eng Computer Engineering, Universitas Diponegoro · Exchange semester at TU Dresden

[LinkedIn](https://www.linkedin.com/in/djievalenciasantoso/) · djievalenciasantoso@gmail.com

---

## Projects

### [PlanPal](https://github.com/djievalencias/planpal-infra) — AI-assisted meeting scheduler for teams

I handled production infrastructure and CI/CD. Built the layered AWS environment in Terraform: public and internal ALBs with WAF for the Next.js web client and Rust backend, Auto Scaling Groups on golden AMIs, RDS Postgres, ElastiCache Redis, a self-hosted NATS cluster as the event backbone, Secrets Manager, and split-horizon Route 53 with ACM. CI/CD runs a credential-less Bitbucket Pipelines gate (tflint, Trivy, Checkov, terraform test) with Atlantis plan/apply via PR comments over a Bitbucket OIDC role, manual gate on prod.

`Terraform` `AWS` `ALB` `ASG` `RDS` `NATS` `Secrets Manager` `Atlantis` `Bitbucket Pipelines` `OIDC`

---

### [Aform](https://github.com/djievalencias/aform) — Form builder with async submission pipeline

I worked on SonarQube SAST integration into the CI pipeline, the staging environment setup, and distributed tracing with Grafana Tempo and Grafana Alloy as the OpenTelemetry collector. Traces go from the Gin HTTP server through the RabbitMQ worker and show up per-request in Tempo.

`SonarQube` `Grafana Tempo` `OpenTelemetry` `Grafana Alloy` `Bitbucket Pipelines` `EC2` `Go`

---

### [Fintrack](https://github.com/djievalencias/fintrack) — Wallet and payment REST API

Built this one solo end to end. Go REST API with wallet and transfer logic, PostgreSQL with migrations, Redis for rate limiting, RabbitMQ worker for async audit logging, AWS S3 with pre-signed URLs, Nginx, systemd on Ubuntu EC2, and Secrets Manager for credentials. Health and readiness endpoints check all four backing services.

`Go` `PostgreSQL` `Redis` `RabbitMQ` `AWS S3` `Secrets Manager` `Nginx` `EC2` `systemd`

---

## Architecture Design

These are standalone architecture studies without a running app. Each one documents the problem, service choices, and the reasoning behind them.

### [AWS Predictive Maintenance](https://github.com/djievalencias/cloud-architecture-designs)
Factory IoT sensor pipeline. Amazon Monitron feeds into Kinesis and Kinesis Data Firehose into an S3 data lake. EventBridge triggers Lambda for alerting and Glue for ETL. Athena and Amazon Managed Grafana for analytics. Designed with cross-account separation between an AWS Managed Account and a Customer Account.

### [AWS Social Media Platform](https://github.com/djievalencias/cloud-architecture-designs)
High-traffic platform design. CloudFront with WAF and Network Firewall, EC2 Auto Scaling behind ELB in public and private subnets, ElastiCache, RDS, Kinesis to Firehose to S3 to Glue to Redshift for analytics, DynamoDB, Rekognition for media processing, and CodeCommit/CodeBuild/CodeDeploy for the DevOps pipeline.

---

## Certifications

| Certification | Year |
|---|---|
| AWS Certified Cloud Practitioner | 2024 |
| GCP Associate Cloud Engineer | 2024 |
| Alibaba Cloud Certified Associate | 2024 |

---

## Stack

**Cloud:** AWS, GCP  
**IaC:** Terraform  
**Languages:** Go, Python, Swift  
**Databases:** PostgreSQL, MySQL, Redis, DynamoDB  
**Messaging:** RabbitMQ, SQS, SNS, Kinesis  
**Observability:** Prometheus, Grafana, OpenTelemetry, Tempo, Grafana Alloy, CloudWatch  
**CI/CD:** GitHub Actions, Bitbucket Pipelines  
**Other:** Docker, Nginx, systemd, SonarQube, AWS Secrets Manager
