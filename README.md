# AWS-Projects

Project-1

Repositories contains all the AWS projects created by me
This IAM policy is essentially a "Power User" policy with a safety net. It grants broad permissions across almost all AWS services but explicitly forbids destructive actions (deletions and terminations).

Here is a breakdown of what this policy does and the potential risks involved.

What This Policy Does
The core logic of this policy relies on the NotAction element.

Broad Access: By using "Effect": "Allow" with "Resource": "*", it grants the user permission to do everything in the AWS account.

The Restriction: The NotAction block lists specific permissions that are excluded from that broad "Allow."

Result: The user can Create, Read, Update, and List resources across all the listed services, but they cannot Delete them.

Key Protected Actions:
Compute: Prevents terminating EC2 instances.

Storage: Prevents deleting S3 buckets/objects and EBS volumes.

Databases: Prevents deleting RDS, DynamoDB, and Redshift clusters.

Identity: Prevents deleting IAM users, roles, or policies (though they can still create them).

Infrastructure: Prevents deleting CloudFormation stacks.
