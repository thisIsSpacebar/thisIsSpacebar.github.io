---
description: |
    This escalation targets an existing lambda with higher privileges.

    The command uploads new code to the lambda which will be executed with higher privileges when the lambda is invoked.

    The process of invoking the lambda will vary depending upon the configuration of the lambda you are modifying.
details:
    AWS-CLI-command:
        - code: |
            aws lambda update-function-code --function-name {target function} --zip-file fileb://{path to zip file}
    required-privileges:
        - code: |
            lambda:InvokeFunction
            OR
            lambda:CreateFunctionUrlConfig
            OR
            lambda:CreateEventSourceMapping
    required-configurations:
        - code: |
            An existing higher privilege lambda role.
    useful-privileges:
        - code: |
            iam:GetPolicy
            lambda:ListFunctions
            lambda:GetFunction
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---