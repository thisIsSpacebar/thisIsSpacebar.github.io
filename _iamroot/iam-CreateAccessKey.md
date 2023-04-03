---
description: |
    This command should be targeted against a user with higher privileges.

    The command creates and returns a new access key pair for the targeted user. It is not possible to target the root user with this command.
details:
    AWS-CLI-command:
        - code: |
            aws iam create-access-key --user-name {target user}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            An existing higher privilege user.
    useful-privileges:
        - code: |
            iam:ListUsers
            iam:ListAttachedUserPolicies
            iam:GetPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---