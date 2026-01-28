🌐 Website Uptime Monitoring System (AWS)
A serverless, AWS-based Website Uptime Monitoring and Alerting System that continuously checks website availability and sends email notifications when the website goes down or recovers.

This project uses Amazon Route 53 Health Checks, Amazon CloudWatch Alarms, and Amazon SNS and is fully compatible with the AWS Free Tier.

🧠 Project Overview

Monitoring website availability is critical for reliability and user trust. This project demonstrates how AWS native services can be used to:

Monitor a website’s health in real time

Detect downtime automatically

Trigger alerts when the website becomes unavailable

Notify users via email using SNS

🏗 Architecture

Services Used:

Amazon Route 53 – Health checks for website monitoring

Amazon CloudWatch – Metrics and alarm evaluation

Amazon SNS – Email notifications

Gmail – Alert delivery endpoint

Flow:

Route 53 performs periodic health checks on the website

Health check publishes metrics to CloudWatch

CloudWatch alarm evaluates HealthCheckStatus

Alarm triggers SNS notification

Email alert is sent to the subscribed user

🚀 Features

✅ Automatic website health monitoring

📉 Detects downtime within 1 minute

📧 Email alerts on website failure

🔁 Alarm state recovery support

💸 Free-tier friendly setup

⚙️ Configuration Details
Route 53 Health Check

Protocol: HTTPS

Port: 443

Request interval: 30 seconds

Failure threshold: 3

Endpoint: Domain name

CloudWatch Alarm

Metric: HealthCheckStatus

Namespace: AWS/Route53

Threshold: Less than 1

Evaluation period: 1 minute

Datapoints to alarm: 1 out of 1

ℹ️ HealthCheckStatus = 1 → Website UP

ℹ️ HealthCheckStatus = 0 → Website DOWN

🔔 Alerting with SNS

SNS Topic: website-uptime-alerts

Protocol: Email

Subscription status: Confirmed

Trigger: Alarm enters ALARM state

📸 Screenshots

Screenshots included in this repository:

Route 53 Health Check configuration

Health check showing Unhealthy status

CloudWatch alarm configuration

Alarm in ALARM state

SNS topic and email subscription

Alert email received in Gmail

🧪 Testing

To test the system:

Use an invalid or temporarily down website

Wait for the health check to fail

Observe CloudWatch alarm entering ALARM state

Verify alert email is received

📚 What I Learned

How Route 53 health checks integrate with CloudWatch

Understanding CloudWatch alarm thresholds

Real-world alerting using SNS

Designing a simple monitoring system using AWS managed services

🔒 Cost Considerations

Uses AWS Free Tier eligible services

No EC2 or compute costs

Minimal Route 53 health check charges
