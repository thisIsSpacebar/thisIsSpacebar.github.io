---
description: |
    This command should be executed against a group you are a member of.

    The command attaches the supplied file to the target group as an inline policy.
details:
    AWS-CLI-command:
        - code: |
            aws iam put-group-policy --group-name {group you are a member of} --policy-name {Policy name} --policy-document file://{path to policy file}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A group you are a member of.
    useful-privileges:
        - code: |
            None
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---