---
description: |
    This command should be targeted against an existing ec2 instance with more privileges than currently possessed.

    The commands stop the instance, update the instance user data and then start the instance. By default, instance user data only executes the first time that an instance is started. However, through the use of a multipart mime file it is possible to reconfigure the instance to run the user data on every restart, and provide code to execute. Instructions on the format of this file can be found [here](https://aws.amazon.com/premiumsupport/knowledge-center/execute-user-data-ec2/). This file must be base64 encoded before being uploaded.
details:
    AWS-CLI-command:
        - code: |
            aws ec2 stop-instances --instance-id {target instance id}
            aws ec2 modify-instance-attribute --instance-id {target instance id} --attribute userData --value file://{path to base64 encoded file}
            aws ec2 start-instances --instance-id {target instance id}
    required-privileges:
        - code: |
            ec2:StopInstances
            ec2:StartInstances
    required-configurations:
        - code: |
            An ec2 instance with more privileges than you.
    useful-privileges:
        - code: |
            ec2:ListInstances
            ec2:GetInstance
            iam:GetRole
    sources:
        - code: |
            Lucas Fedyniak-Hopes
---



