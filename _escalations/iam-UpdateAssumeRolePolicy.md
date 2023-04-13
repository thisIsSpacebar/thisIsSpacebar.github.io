---
description: |
    This command should be targeted against a role you have the permission to assume via **sts:AssumeRole** but do not have the permission within the Assume Role Policy Document.

    The command attaches the supplied json to the targeted tole as a new trust policy. By updating the Assume Role Policy Document to include your user, **sts:AssumeRole** can be used to assume the higher privileged role.
details:
    AWS-CLI-command:
        - code: |
            aws iam update-assume-role-policy --role-name {target role} --policy-document file://{path to trust policy json}
    required-privileges:
        - code: |
            sts:AssumeRole
    required-configurations:
        - code: |
            A role you have sts:AssumeRole permissions on with higher privileges.
    useful-privileges:
        - code: |
            iam:ListRoles
            iam:GetPolicy
            iam:ListGroups
            iam:GetGroups
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---