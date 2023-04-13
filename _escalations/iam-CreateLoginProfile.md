---
description: |
    This command should be targeted against a user with higher privileges.

    The command creates a password for a user who does not already have one. It is not possible to target the root user with this command.
details:
    AWS-CLI-command:
        - code: |
            aws iam create-login-profile --user-name {target user} --password {password} --no-password-reset-required
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            An existing higher privilege user who does not have a password configured.
    useful-privileges:
        - code: |
            iam:ListUsers
            iam:ListAttachedUserPolicies
            iam:GetPolicy
            iam:GetLoginProfile
            iam:GetAccountPasswordPolicy
            iam:DeleteLoginProfile
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---