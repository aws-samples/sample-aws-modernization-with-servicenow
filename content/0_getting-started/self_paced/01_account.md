---
title: "Create an AWS IAM User with Cloudformation"
chapter: false
weight: 1
---

Note: 
Only complete this section if you are running the workshop on your own. If you are at an AWS hosted event (such as re\:Invent, Kubecon, Immersion Day, etc), go to [Start the workshop at an AWS event](../aws_event/). Keep in mind, you may incur costs by participating in this workshop. Please navigate to the ../Cleanup

Your account must have the ability to create new IAM Users and scope other IAM permissions.




1. Navigate to [Cloudformation](https://console.aws.amazon.com/cloudformation/) and click on Create Stack -> With new resources standard.

![Create Stack](/images/create-stack.png)


2. Select "Build from Infrastructure Composer":
![Build from Infrastructure Composer](/images/infrastructure-composer.png)

3. Click Template:
![Click Template](/images/click-template.png)

4. Copy/Paste the Cloudformation template below into the blank field:

```sh
AWSTemplateFormatVersion: '2010-09-09'
Description: 'Create IAM User with Access Key stored in Secrets Manager and Bedrock permissions'

Resources:
  MyIAMUser:
    Type: AWS::IAM::User
    Properties:
      UserName: ServiceNow_User
      ManagedPolicyArns:
        - !Ref BedrockUserPolicy

  BedrockUserPolicy:
    Type: AWS::IAM::ManagedPolicy
    Properties:
      ManagedPolicyName: BedrockUserPolicy
      PolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Action:
              - bedrock:InvokeModel
              - bedrock:ListFoundationModels
              - bedrock:GetFoundationModel
              - bedrock:ListCustomModels
              - bedrock:GetCustomModel
              - bedrock:ListModelInvocationLoggingConfigurations
              - bedrock:ListPromptsForCustomModel
              - bedrock:ListPromptTemplates
              - bedrock:GetPromptTemplate
            Resource: '*'
          - Effect: Allow
            Action:
              - iam:PassRole
            Resource: '*'
            Condition:
              StringEquals:
                iam:PassedToService: bedrock.amazonaws.com

  MyIAMUserAccessKey:
    Type: AWS::IAM::AccessKey
    Properties:
      UserName: !Ref MyIAMUser

  MySecret:
    Type: AWS::SecretsManager::Secret
    Properties:
      Name: MyUserAccessKey
      Description: 'Access key for ServiceNow_User'

  StoreSecretFunction:
    Type: AWS::Lambda::Function
    Properties:
      Runtime: python3.8
      Handler: index.handler
      Role: !GetAtt LambdaExecutionRole.Arn
      Code:
        ZipFile: |
          import boto3
          import cfnresponse
          def handler(event, context):
            try:
              if event['RequestType'] == 'Create':
                secret_name = event['ResourceProperties']['SecretName']
                access_key_id = event['ResourceProperties']['AccessKeyId']
                secret_access_key = event['ResourceProperties']['SecretAccessKey']
                
                secrets_manager = boto3.client('secretsmanager')
                secrets_manager.put_secret_value(
                  SecretId=secret_name,
                  SecretString='{"AccessKeyId":"' + access_key_id + '","SecretAccessKey":"' + secret_access_key + '"}'
                )
              cfnresponse.send(event, context, cfnresponse.SUCCESS, {})
            except Exception as e:
              print(e)
              cfnresponse.send(event, context, cfnresponse.FAILED, {})

  StoreSecretCustomResource:
    Type: Custom::StoreSecret
    Properties:
      ServiceToken: !GetAtt StoreSecretFunction.Arn
      SecretName: !Ref MySecret
      AccessKeyId: !Ref MyIAMUserAccessKey
      SecretAccessKey: !GetAtt MyIAMUserAccessKey.SecretAccessKey

  LambdaExecutionRole:
    Type: AWS::IAM::Role
    Properties:
      AssumeRolePolicyDocument:
        Version: '2012-10-17'
        Statement:
          - Effect: Allow
            Principal:
              Service: lambda.amazonaws.com
            Action: sts:AssumeRole
      ManagedPolicyArns:
        - arn:aws:iam::aws:policy/service-role/AWSLambdaBasicExecutionRole
      Policies:
        - PolicyName: SecretsManagerAccess
          PolicyDocument:
            Version: '2012-10-17'
            Statement:
              - Effect: Allow
                Action:
                  - secretsmanager:PutSecretValue
                Resource: !Ref MySecret

Outputs:
  SecretsManagerLink:
    Description: "Link to the Credentials in AWS Secrets Manager"
    Value: !Sub "https://${AWS::Region}.console.aws.amazon.com/secretsmanager/home?region=${AWS::Region}#!/secret?name=${MySecret}"
```

5. Click create template:

![Create Template](/images/create-template.png)

6. Click confirm template:

![Confirm Template](/images/confirm-template.png)

7. Click Next:

![Next](/images/next.png)

8. Specify the stack name and click next:

![Login URL](/images/stack-name.png)

9. Scroll down the page and click the checkbox and click next:

![Login URL](/images/checkbox.png)

10. Scroll down and click Submit:

![Login URL](/images/submit.png)

11. Navigate to Outputs and click on the SecretsManagerLink which will direct you to the IAM access-key and Secret:

![Login URL](/images/outputs.png)

12. Click on retrieve secret value and copy the secret access id and secret access key to a notepad:

![Login URL](/images/secret.png)

Success! Now you can wait for the instructions provided by the instructor to continue the workshop!
