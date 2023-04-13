---
description: |
    This command should be targeted against a user you control.

    The command attaches a higher privilege policy to a user you control. Depending on the policies allowed within the grant, this permission can be used to apply the **arn:aws:iam::aws:policy/AdministratorAccess** for full compromise of the environment.
details:
    AWS-CLI-command:
        - code: |
            aws iam attach-user-policy --user-name {target user account} --policy-arn {target policy arn}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A user account under your control.
    useful-privileges:
        - code: |
            iam:ListPolicies
            iam:GetPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---