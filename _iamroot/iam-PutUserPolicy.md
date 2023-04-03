---
description: |
    This command should be executed against a user you control.

    The command attaches the supplied file to the target user as an inline policy.
details:
    AWS-CLI-command:
        - code: |
            aws iam put-user-policy --user-name {User you control} --policy-name {Policy name} --policy-document file://{path to policy file}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A user you control.
    useful-privileges:
        - code: |
            None
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---