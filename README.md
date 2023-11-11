# QTM-350 Final Project Spring 23
The following demo will demonstrate steps to upload files in S3 to digitalize columns of data to your computer.

## Amazon Textract
Amazon Textract is an Amazon Web Services ML service that can extract data and text through scanned files, including images, PDFs, and more. It can automatically convert numbers and text to digital files, which is valuable for preservation of information. 

## Step 1: Uploading file(s) to S3 in a New Bucket
The following steps will help you create an S3 bucket in your AWS to upload files od scanned documents.
1. After logging into AWS services, search and choose S3 in the search bar.
2. Select create bucket and use a unique name.
3. Keep the default settings and select 'Next'.
4. Create bucket.
5. Select created bucket from the console and click 'Upload.'
6. Select your desired file and dragging to upload box.
7. Scroll down to select 'Upload.'

## Step 3: Using Textract from S3
The following steps will guide using Textract in AWS.
1. On the AWS console, click on 'Textract.'
2. Select 'Try Amazon Textract.'
3. Scroll down to the bottom, and select 'Upload documents.'
4. Keep 'Import documents from S3 bucket' selected.
5. Click on 'Browse S3.'
6. Select bucket.
7. Click on 'Choose.'
8. In features, choose 'AnalyzeDocument - Tables.'
9. Click 'Start Processing.'
10. Wait until the results under 'Status' changes from 'Processing' to 'Ready for Download.'
11. Select files and click on 'Download results.'
12. Open up the Excel Table to observe results. 
