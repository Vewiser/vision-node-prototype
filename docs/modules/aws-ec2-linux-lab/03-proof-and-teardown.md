# 03 // Proof, Cost Review, and Teardown

Every EC2 lab ends with evidence and cleanup.

## Lab-note template

```markdown
# EC2 Linux Lab // YYYY-MM-DD

## Goal
What I intended to learn.

## Build
- Distribution:
- Instance class:
- Connection method:
- Services:
- Storage:
- Monitoring:

## Commands understood
- Command:
- What it does:
- Why I used it:

## Failure and recovery
- Symptom:
- Evidence:
- Cause:
- Fix:
- Validation:

## Cost review
- Session length:
- Resources created:
- Resources removed:
- Cost dashboard checked:

## Lesson
What I can now explain or repeat without guessing.

## Next
One controlled next step.
```

## Sanitization checklist

Never publish:

- AWS account or organization IDs
- Access-key IDs or secret keys
- Session tokens
- Private SSH keys
- Instance IDs
- Real public or private IP addresses
- Public DNS names
- VPC, subnet, security-group, volume, snapshot, AMI, or role IDs
- Terraform state or unredacted plans
- Billing-account information
- Console screenshots containing identity or notification details

## Teardown order

1. Save only sanitized notes and reproducible configuration.
2. Stop the practice service.
3. Copy disposable proof data only if the exercise requires it.
4. Terminate the EC2 instance.
5. Delete unneeded EBS volumes.
6. Delete unneeded snapshots and custom images.
7. Release unused Elastic IP addresses.
8. Remove temporary security groups when safe.
9. Remove temporary key pairs.
10. Remove lab-only IAM roles or policies when no longer required.
11. Review CloudWatch log groups, alarms, and custom metrics.
12. Review load balancers, NAT gateways, endpoints, and other accidentally created resources.
13. Check the EC2 resource inventory in every region used.
14. Review Cost Explorer and budget status after billing data updates.

A stopped instance can still leave chargeable storage or addresses. A budget alert can arrive after costs are incurred.

## Proof 002 // EC2 Linux Operator

Proof 002 is complete when the operator can show, without exposing secrets:

- A secure instance-launch checklist
- Successful SSH and Session Manager access
- A user/permissions exercise
- A service installed, inspected, restarted, and removed
- A disposable volume mounted and recovered
- One diagnosed networking failure
- One monitoring view
- One automated rebuild
- One controlled failure and recovery
- A clean termination and resource-inventory check
- A concise Ubuntu versus Amazon Linux comparison

## Final explanation

Be able to say:

> I can create a Linux server in AWS, connect securely, manage the operating system, troubleshoot services and networking, recover from controlled mistakes, rebuild it from documentation or code, and remove every resource when the lab is finished.
