+++ 
title = "Task 4a: IAM policies and roles - Lambda" 
chapter = false 
weight = 4 
+++

In this task we will create IAM policies and roles required by Lambda and Elastic Transcoder.

1. Go to Services *search box* > IAM

1. We will create first the IAM policy and role which will be assumed by the Lambda function that will process the **Elastic Transcoder** pipeline notifications and push those notifications to **CloudWatch Logs**. From the left pane, click on **Policies**.

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. In the **Create policy** page, click on **JSON**

1. Clean up the policy editor window and paste the below JSON document

````JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:PutLogEvents",
                "logs:DescribeLogStreams",
                "logs:CreateLogGroup"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
````

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In the **Review policy** section, for **Name** type `gif-factory-lambda-logs-proc-policy`

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. Now you will create a IAM role and attach the IAM policy you just created. Fromm the left pane, click on **Roles**

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Under **Choose a use case**, click on **Lambda**

1. Click on <img src="../images/next-permissions.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Under **Attach permissions policies**, in the *Search box*, type `gif-factory-lambda-logs-proc-policy`. Once you see the IAM policy, click to select it

    <img src="../images/select-policy-1.png" alt="drawing" width="500"/>

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In **Role name** type `gif-factory-lambda-logs-proc-role`

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Now we will create the IAM policy and role the Lambda function which will initiate the **Elastic Transcoder** job, will assume. From the left pane, click on **Policies**.

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. In the **Create policy** page, click on **JSON**

1. Clean up the policy editor window and paste the below JSON document

````JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "elastictranscoder:*",
                "s3:*",
                "logs:*"
            ],
            "Resource": "*"
        }
    ]
}
````

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In the **Review policy** section, for **Name** type `gif-factory-lambda-transcode-policy`

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. Now you will create a IAM role and attach the IAM policy you just created. From the left pane, click on **Roles**

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Under **Choose a use case**, click on **Lambda**

1. Click on <img src="../images/next-permissions.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Under **Attach permissions policies**, in the *Search box*, type `gif-factory-lambda-transcode-policy`. Once you see the IAM policy, click to select it

    <img src="../images/select-policy-2.png" alt="drawing" width="500"/>

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In **Role name** type `gif-factory-lambda-transcode-role`

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>


----








1. Now we will add this **Lambda function** as an subscriber to the SNS topic created in **Task 1** *step 23*. Go to Services *search box* > SNS

In this task we will create and configure some other services, we'll start with an IAM policy and role

1. Go to Services *search box* > IAM

1. We will create an IAM policy to later attach to an IAM role, which will be assumed by the Lambda function that will process the **Elastic Transcoder** pipeline notifications and push those notifications to **CloudWatch Logs**. From the left pane, click on **Policies**. 

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. In the **Create policy** page, click on **JSON**

1. Clean up the policy editor window and paste the below JSON document

````
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogStream",
                "logs:PutLogEvents",
                "logs:DescribeLogStreams",
                "logs:CreateLogGroup"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
````

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In the **Review policy** section, for **Name** type `gif-factory-lambda-logs-proc-policy`

1. Click on <img src="../images/create-policy.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. Now you will create a IAM role aand attach the IAM policy you just created. Fromm the left pane, click on **Roles**

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Under **Choose a use case**, click on **Lambda**

1. Click on <img src="../images/next-permissions.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Under **Attach permissions policies**, in the *Search box*, type `gif-factory-lambda-logs-proc-policy`. Once you see the IAM policy, click to select it

    <img src="../images/select-policy-1.png" alt="drawing" width="500"/>

1. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In **Role name** type `gif-factory-lambda-logs-proc-role`

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Now you will create a Lambda function which will be triggered when a **Elastic Transcoder** job initiates. Go to Services *search box* > Lambda

1. Click on <img src="../images/create-function.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Select **Author from scratch**

1. In **Function name** type `gif-factory-lambda-logs-proc`

1. In **Runtime** select **Python 3.8**

1. Click on **Change default execution role**

1. Select **Use an existing role**

1. Under **Existing role** display the options and select `gif-factory-lambda-logs-proc-role`

1. Click on <img src="../images/create-function.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. The Lambda function source code is stored for you in a S3 bucket, you'll need to upload it from there to create your Lambda function. To import the source follow this steps. In the **Code source** section, click on **Upload from** and the select **Amazon S3 location**

    <img src="../images/upload-from-s3-lambda-code-1.png" alt="drawing" width="800"/>

1. Copy and paste this URL under **Amazon S3 link URL**

    ````
    s3://ee-assets-prod-us-east-1/modules/5f3d25ca9f614189b5235736eb1ba589/v1/lambda_function_logs.zip
    ````

    <img src="../images/upload-from-s3-url-1.png" alt="drawing" width="600"/>

1. Click **Save**

1. To look at the code uploaded from S3, click on *lambda-parse-sns-logs.py*

    <img src="../images/click-on-lambda-code-1.png" alt="drawing" width="250"/>

1. This **Lambda function** will sends logs to **CloudWatch Logs**, we will use the *Environmet variables* feature within **Lambda** to adjust the function's behavior without updating code.

> Learn more: https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html

1. Click on Lambda's **Configuration** tab

    <img src="../images/click-on-config-tab.png" alt="drawing" width="400"/>

1. Click on **Environment variables**

    <img src="../images/click-on-env-vars.png" alt="drawing" width="200"/>

1. Click on **Edit**

1. Click *twice* on **Add environment variable**



> MISSING Lambda explanation and diagram

1. Now we will add this **Lambda function** as an subscriber to the SNS topic created in **Task 1** *step 23*. Go to Services *search box* > SNS



