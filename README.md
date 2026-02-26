# data


####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####


Yes. If you want AWS managed policies only for a GitHub OIDC deploy role (SaaS Builder Toolkit), use either:

AdministratorAccess (quick POC, not least-privilege)
Or a more controlled set (common for SaaS Builder-style serverless deployments):

AWSCloudFormationFullAccess
IAMFullAccess
AWSLambda_FullAccess
AmazonAPIGatewayAdministrator
AmazonDynamoDBFullAccess
AmazonS3FullAccess
CloudWatchLogsFullAccess
AmazonEventBridgeFullAccess
AWSStepFunctionsFullAccess
SecretsManagerReadWrite
AmazonSSMFullAccess
AmazonCognitoPowerUser (if your stack uses Cognito)
AWSKeyManagementServicePowerUser (if using customer-managed KMS keys)
For production, this is still broad; best practice is to replace with a custom least-privilege policy after first successful deployment.


"quick POC, not least-privilege)" what is this 

“Quick POC, not least-privilege” means:

Quick POC = fast setup for a Proof of Concept so you can deploy quickly.
Not least-privilege = permissions are broader than necessary (for example AdministratorAccess), which is not ideal for security.
