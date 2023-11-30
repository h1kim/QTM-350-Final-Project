# QTM-350 Final Project Fall 23
The following demo will demonstrate steps to upload files in S3 to digitalize columns of data to your computer.

## Amazon Textract
Amazon Textract is an Amazon Web Services ML service that can extract data and text through scanned files, including images, PDFs, and more. It can automatically convert numbers and text to digital files, which is valuable for preservation of information. 

## Step 1: Uploading file(s) to S3 in a New Bucket
The following steps will help you create an S3 bucket in your AWS to upload files od scanned documents.
1. After logging into AWS services, search and choose S3 in the search bar.
2. Select create bucket and use a unique name. Note that bucket names can include only lower case letters, dots, hyphens, and numbers (For more specific rules for Bucket naming on Amazon S3, see https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html.).
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


## Architecture: Textract Flow Chart
To better illustrate the process, we created the following flow chart to demonstrate the AWS workstream:
![image](https://github.com/h1kim/QTM-350-Final-Project/assets/92637998/c6b1f559-e406-4284-8ef5-a6905ade92ab)
First, an image file or PDF file is uploaded to Amazon S3, a storage location. Then, Amazon S3 uses the function Fn-A to call AWS Textract as a key-value pair from the file source. Then, Textract automatically extracts data from the files within S3. 

Here is an example of an example workflow:
S3
1. S3 Bucket: The user uploads images and pdf files of images to an S3 bucket.
2. Amazon Textract: Amazon Textract automatically begins processing the documents
3. Amazon Textract Processing: Textract processes the files, extracting numerical and textal data.
4. S3 Output: The Textract output can be stored into a different S3 bucket or sent to another AWS service for further analysis.
5. Sagemaker Processing: Sagemaker can be used to build a custom model or for further processing of extracted data.
6. Result: The output from Sagemaer can also be stored in a different S3 or used for further updates with other AWS services.

As AWS regularly updates and alters its services, it is important to note that the architecture can vary on different uses cases. It is recommended to keep in update with the latest AWS documentation for the most upto-date information on Textract's workflow. 

For more in-depth information about invoking the Lambda function using Amazon S3, refer to https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html.
## Supported Regions
Amazon Textract API is available in the regions below:
- US East (N. Virginia)
- US East (Ohio)
- US West (Northern California)
- US West (Oregon)
- Asia Pecific (Mumbai)
- Asia Pecific (Seoul)
- Asia Pecific (Singapore)
- Asia Pecific (Sydney)
- Canada (Central)
- Europe (Frankfurt)
- Europe (Ireland)
- Europe (London)
- Europe (Paris)
- AWS GovCloud (US-East)
- AWS GovCloud (US-West)

For more information on tiers and pricing, refer to https://aws.amazon.com/textract/pricing/
