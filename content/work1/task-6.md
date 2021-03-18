+++ 
title = "Task 6: SNS Topic and subscription" 
chapter = false 
weight = 6 
+++

1. Now you will create an Simple Notification Service (SNS) topic, which will be invoked when an **Elastic Transcoder** job initiates. Go to Services *search box* > SNS

1. From the left pane, click on **Topics**

1. Click on <img src="../images/create-topic.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. In the **Details** section, under **Type**, select **Standard**

1. Under **Name** type `gif-factory-topic`

1. Click on <img src="../images/create-topic.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. Now you will create a subscription, which will trigger a Lambda function, in this case it will invoke the function called `gif-factory-lambda-logs-proc` which will read the **Elastic Transcoder** job events, extract values and will be sending the event information to **CloudWatch Logs**. Click on <img src="../images/create-subscription.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="130"/>

1. In the **Details** section, under **Protocol** select **AWS Lambda**

1. Under **Endpoint**, type `gif-factory-lambda-logs-proc` and click on the option displayed to select it

1. Click on <img src="../images/create-subscription.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="130"/>