---
description: |
    This command should be executed against a group with higher privleges.

    The command adds the provided username to the target group, thereby allowing the user to inherit increased privileges.
details:
    AWS-CLI-command:
        - code: |
            aws iam add-user-to-group --group-name {target group] --user-name {user you control}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            An existing higher privileged group.
    useful-privileges:
        - code: |
            iam:ListGroups
            iam:ListAttachedGroupPolicies
            iam:GetPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---