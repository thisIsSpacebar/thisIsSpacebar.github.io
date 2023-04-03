---
description: |
    This command should be executed against a customer managed policy that is already attached or can be attached to a user or role you control, or a group you are a member of.

    This escalation changes the policy to an already existing more highly privileged version.
details:
    AWS-CLI-command:
        - code: |
            aws iam set-default-policy-version --policy-arn {policy arn} --version-id v{privileged version number}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            A customer managed policy attached to a user or role you control, or a group you are a member of.
            This policy must have a more highly priveleged version.
    useful-privileges:
        - code: |
            iam:ListAttachedUserPolicies
            iam:ListAttachedRolePolicies
            iam:ListAttachedGroupPolicies
            iam:ListGroups
            iam:GetGroup
            iam:ListPolicyVersions
            iam:GetPolicyVersion
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
---