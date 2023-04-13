---
description: |
    This command should be executed against a role you control.

    The command attaches the supplied file to the target role as an inline policy.
details:
    AWS-CLI-command:
        - code: |
            aws iam put-role-policy --role-name {role you control} --policy-name {Policy name} --policy-document file://{path to policy file}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A role you control.
    useful-privileges:
        - code: |
            None
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---