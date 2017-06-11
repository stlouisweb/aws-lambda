AWS Serverless applications with Lambda, API Gateway and DynamoDB.

http://docs.aws.amazon.com/lambda/latest/dg/with-on-demand-https-example.html

**AWS Lambda** is a service that allows you to host individual functions on AWS and execute the functions on demand without the need to maintain a dedicated cloud server.

Lambda functions can be invoked by a number of triggers including scheduled jobs or HTTP requests. You are only charged when the function executed (not to just host the function).

**AWS API Gateway** is a tool that provides a REST interface to access services and resources managed in AWS (like Lambda functions).    
Amazon API Gateway also adds a layer between your application users and your app logic that enables the following:

- Ability to throttle individual users or requests.
- Protect against Distributed Denial of Service attacks.
- Provide a caching layer to cache response from your Lambda function.

**AWS DynamoDB** is a NoSQL Database provided by AWS that works well with other AWS tools.

## Step 1 Prepare

- Signed up for an AWS account and created an administrator user in the account.
- Installed and set up the AWS CLI.

## Step 2: Create a Lambda Function

### 2.1 Create a Deployment package

Write the function code in a file called `LambdaFunctionOverHttps.js`

Then:    
- Save the file as LambdaFunctionOverHttps.js
- Zip the LambdaFunctionOverHttps.js file as LambdaFunctionOverHttps.zip

### 2.2 Create the Execution Role (IAM Role)

Use AWS service role of the type AWS Lambda – This role grants AWS Lambda permissions to assume the role.

1. Sign in to IAM Console: https://console.aws.amazon.com/iam/
2. Follow the steps in Creating a Role to Delegate Permissions to an AWS Service in the IAM User Guide to create an IAM role (execution role). As you follow the steps to create a role, note the following:

- In Role Name, use a name that is unique within your AWS account (for example, lambda-gateway-execution-role).
- In Select Role Type, choose AWS Service Roles, and then choose AWS Lambda. This grants the AWS Lambda service permissions to assume the role.
- You create an IAM role without attaching a permissions policy in the console. After you create the role, you update the role, and then attach the following permissions policy to the role.
