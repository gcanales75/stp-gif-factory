+++ 
title = "Task 2: DynamoDB table" 
chapter = false 
weight = 2 
+++

1. Now you will create a DynamoDB table to be used as a searchable index 

1. Go to Services *search box* > DynamoDB

1. From your left pane, click on **Tables**

1. Click <img src="../images/create-table.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="90"/>

1. In the **Table details** section, complete the information

	| Key | Value  |
	|---|---|
	| Table name  | gif-factory-index  |
	| Partition key | OpId |

1. In the **Settings** section, select **Customize settings**

1. In the **Read/write capacity settings**, under **Capacity mode**, select **On-demand**

1. At the bottom on the page click on <img src="../images/create-table.png" style="border: 0; display:inline; margin: 0 2px; box-shadow: none" alt="alt text" width="100"/>