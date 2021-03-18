+++ 
title = "Task 8: S3 event notification" 
chapter = false 
weight = 8 
+++

1. Now you will create an **S3** event notification, which will invoke the Lambda function called `gif-factory-lambda-transcoder` every time a new object get uploaded to the S3 bucket. Go to Services *search box* > S3

1. In the **Buckets** section, type your project S3 bucket name

    <img src="../images/find-s3-bucket.png" alt="drawing" width="800"/>

1. Click on your **S3** bucket

1. Click on **Properties**

    <img src="../images/click-on-properties.png" alt="drawing" width="600"/>

1. Scroll down to the **Event notifications** section, and click on <img src="../images/create-event-notification.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="170"/>

1. In the **General configuration** section, under **Event name** type `gif-factory-new-mp4`

1. Under **Suffix - optional**, type `.mp4`

1. in the **Event types** section click the checkbox next to **Put**

    <img src="../images/event-type-put.png" alt="drawing" width="500"/>

1. In the **Destination** section, under **Destination** select **Lambda function**

1. Under **Specify Lambda function**, select **Choose from your Lambda functions**

1. Under **Lambda function**, type `gif-factory-lambda-transcoder`

    <img src="../images/event-notification-destination.png" alt="drawing" width="600"/>

1. Click on <img src="../images/save-changes.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="110"/>

