+++ 
title = "Task 5b: Lambda function - Trigger Transcoder" 
chapter = false 
weight = 5 
+++

1. Now you will create a Lambda function which will be triggered when a new MP4 file is uploaded in your S3 bucket (Event notification will be created in Task 8). This Lambda function will initiate an **Elastic Transcoder** job. Go to Services *search box* > Lambda

1. Click on <img src="../images/create-function.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Select **Author from scratch**

1. In **Function name** type `gif-factory-lambda-transcoder`

1. In **Runtime** select **Python 3.8**

1. Click on **Change default execution role**

1. Select **Use an existing role**

1. Under **Existing role** display the options and select `gif-factory-lambda-transcode-role`

1. Click on <img src="../images/create-function.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="110"/>

1. The Lambda function source code is stored for you in a S3 bucket, you'll need to upload it from there to create your Lambda function. To import the source follow this steps. In the **Code source** section, click on **Upload from** and the select **Amazon S3 location**

    <img src="../images/upload-from-s3-lambda-code-1.png" alt="drawing" width="800"/>

1. Copy and paste this URL under **Amazon S3 link URL**

    ````
    s3://ee-assets-prod-us-east-1/modules/5f3d25ca9f614189b5235736eb1ba589/v1/lambda_function_transcoder.zip
    ````

    <img src="../images/upload-from-s3-url-2.png" alt="drawing" width="600"/>

1. Click **Save**

1. Take a look at the code uploaded from S3, click on *lambda_function_transcoder.py*. Do not edit the Python code.

    <img src="../images/click-on-lambda-code-2.png" alt="drawing" width="250"/>

1. We need to update the Lambda function default timeout, from 3 seconds to 10 seconds. Click on Lambda's **Configuration** tab

    <img src="../images/click-on-config-tab.png" alt="drawing" width="400"/>

1. Click on **General configuration**

    <img src="../images/click-on-general-config.png" alt="drawing" width="200"/>

1. Click on **Edit**

1. In the **Basic settings** section, under **Timeout**, change from `3`seconds, to `10` seconds

1. Click on <img src="../images/click-on-save.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="50"/>



> MISSING Lambda explanation and diagram

