+++ 
title = "Task 4b: IAM policies and roles - Elastic Transcoder role" 
chapter = false 
weight = 4 
+++

1. Now we will create the **IAM role** required by **Elastic Transcoder** to read files and write to S3 and send notifications to SNS. This role will use an *AWS Managed Policy* called **AmazonElasticTranscoderRole**. From the left pane, click on **Roles**

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>

1. Under **Choose a use case**, click on **Elastic Transcoder**

1. Click on <img src="../images/next-permissions.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>

1. Under **Attach permissions policies**, you will see listed the *AWS Managed Policy* called **AmazonElasticTranscoderRole**. Click on <img src="../images/next-tags.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="70"/>

1. Click on <img src="../images/next-review.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="85"/>

1. In **Role name** type `gif-factory-transcoder-iam-role`

1. Click on <img src="../images/create-role.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="80"/>