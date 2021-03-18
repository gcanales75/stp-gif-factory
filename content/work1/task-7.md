+++ 
title = "Task 7: Elastic Transcoder pipeline" 
chapter = false 
weight = 7 
+++

1. Now you will create an **Elastic Transcoder** pipeline, which will be iniated when the Lambda function called `gif-factory-lambda-transcoder` get invoked. Go to Services *search box* > Elastic Transcoder

1. Click on <img src="../images/create-pipeline.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="130"/>

1. In **Pipeline Name** type `gif-factory-pipeline`

1. In **Input Bucket** type the name of the bucket you created in *Task 1*

1. In **IAM Role** select `gif-factory-transcoder-iam-role`

1. Under **Configuration for Amazon S3 Bucket for Transcoded Files and Playlists**, in **Bucket** type again the name of the bucket you created in *Task 1*

1. For **Storage Class** select **Standard**

1. Repeat steps 5 and 6 for the fields under **Configuration for Amazon S3 Bucket for Thumbnails**

1. Click on **Notifications (Optional)**

1. You will see 4 type of events:

    * On Progressing Event
    * On Warning Event
    * On Completion Event
    * On Error Event

    On all 4 events select **Use an existing SNS topic** and in **Select a Topic** select `gif-factory-topic`

    <img src="../images/transcoder-notifications.png" alt="drawing" width="500"/>

1. Click on <img src="../images/create-pipeline-2.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>