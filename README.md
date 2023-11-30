# QTM-350 Final Project Fall 23

## Amazon Textract Demo
This README provides a step-by-step instructions for uploading files to Amazon S3 and using
Textract to convert scanned documents into digital files. Our project focuses on utilizing Amazon Textract to extract data and text from scanned files such as images and PDFs. The goal is for columns of data to be accessible on your computer from an originally paper format. 

Here is the link to our project blog: https://final-project-ron.s3.amazonaws.com/350_final_project.html

## Amazon Textract
Amazon Textract is an Amazon Web Services ML service that can extract data and text through scanned files, including images, PDFs, and more. It can automatically convert numbers and text to digital files, which is valuable for preservation of information. 

## Step 1: Uploading file(s) to S3 in a New Bucket
The following steps will help you create an S3 bucket in your AWS to upload files od scanned documents.
1. After logging into AWS services, search and choose S3 in the search bar.
2. Select 'Create Bucket' and create a unique name. Note that bucket names can include only lower case letters, dots, hyphens, and numbers (For more specific rules for Bucket naming on Amazon S3, see https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html.).
3. Select a Region to create your bucket it
4. Keep the default settings and select 'Next'.
5. Create bucket.
6. Select created bucket from the console and click 'Upload.'
7. Select your desired file and dragging to upload box.
8. Scroll down to select 'Upload.'
9. Select the checkbox next to the file in the bucket.

## Step 2: Using Textract from S3
The  steps below guides how to use Textract in AWS.
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

For further clarification, feel free to visit https://aws.amazon.com/getting-started/hands-on/extract-text-with-amazon-textract/?ref=gsrchandson

## Step 3: Our Project: Testing Degree of Blurriness and Mismatched Rate of Extracted Data
The following steps will outline a general procedure of how to test the accuracy of extracted data with different degrees of data in Python.
1. Upload images or files of data with varying degrees of blurriness in a folder either on the computer or in S3.
2. Call the image path.
3. Create a dataframe to store the results from Step 2 above using "pd.DataFrame()" function.
4. Calculate the confidence intervals of the dataframe created, and save results to the new dataframe.
5. Extract the output of the dataframe from the images, and compile into a list.
6. For visualization, use the package 'matplotlib.pyplot' to label degree of blurriness on the x-axis and mean confidence on the y-axis.

## Architecture: Textract Flow Chart
To better illustrate the process, we created the following flow chart to demonstrate the AWS workstream:
![image](https://github.com/h1kim/QTM-350-Final-Project/assets/92637998/c6b1f559-e406-4284-8ef5-a6905ade92ab)
First, an image file or PDF file is uploaded to Amazon S3, a storage location. Then, Amazon S3 uses the function Fn-A to call AWS Textract as a key-value pair from the file source. Then, Textract automatically extracts data from the files within S3. 

Here is an example of an example workflow:
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

For more information on tiers and pricing, refer to https://aws.amazon.com/textract/pricing/)https://aws.amazon.com/textract/pricing/

## Resources Used
1. AWS S3 Features - The S3 bucket provides scalable, durable, and secure storage for our documents from which Amazon Textract can fetch for analysis. https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
3.Amazon Textract Documentation - The API is called to analyze the documents stored in the S3 bucket. [https://docs.aws.amazon.com/textract/)https://docs.aws.amazon.com/textract/)](https://docs.aws.amazon.com/textract/)
4. Textract Applications and Uses - There are various use cases for Amazon Textract, such as natural language processing, capture of data from various sources, and automating data processing.
[https://docs.aws.amazon.com/textract/latest/dg/sync.html)https://docs.aws.amazon.com/textract/latest/dg/sync.html](https://docs.aws.amazon.com/textract/latest/dg/what-is.html)https://docs.aws.amazon.com/textract/latest/dg/what-is.html
