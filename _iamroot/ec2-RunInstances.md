---
description: |
    This escalation attaches an existing EC2 Instance Profile to a newly created instance and starts it running.

    The command accepts a file containing a bash script for the host to execute. This should be used to execute higher privileged commands within the environment. Using an amazon linux AMI allows the use of other AWS CLI commands within the bash script.

    **EC2 Instance connect**, **Session Manager**, **SSH** and **EC2 Serial** are other methods that can be used to connect to the new instance in order to gain access to the role. These methods may require additional permissions or specific security group configurations in order to be used.
details:
    AWS-CLI-command:
        - code: |
            aws ec2 run-instances --image-id ami-084e8c05825742534 --count 1 --instance-type t2.micro --iam-instance-profile Name={target instance profile} --user-data file://{bash script}
    required-privileges:
        - code: |
            iam:PassRole
    required-configurations:
        - code: |
            An existing higher privilege EC2 Instance Profile.
    useful-privileges:
        - code: |
            iam:ListRoles
            iam:ListAttachedRolePolicies
            iam:GetPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---