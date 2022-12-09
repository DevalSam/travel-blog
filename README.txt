I have deployed a static website on AWS

This website was deployed using S3, CloudFront, and IAM.

The following files were included: 

index.html - The Index document for the website.
/img - The background image file for the website.
/vendor - Bootssrap CSS framework, Font, and JavaScript libraries needed for the website to function.
/css - CSS files for the website.
screenshots of the different stages of the project setup 

The project can be completed with the following steps 

* Create an S3 bucket with public access configurations 

* Upload the index.html file and the also upload the img,css, and the vendor folders.  
  please ensure that the file and folders are uploaded to the parent directory
   
* Secure the bucket with an IAM policy as shown below 
  
{
"Version":"2012-10-17",
"Statement":[
 {
   "Sid":"AddPerm",
   "Effect":"Allow",
   "Principal": "*",
   "Action":["s3:GetObject"],
   "Resource":["arn:aws:s3:::your-website/*"]
 }
]
} 

* Configure the S3 bucket to enable static website hosting and also ensure to specify the 
  index.html file as the document for the default and the error pages respectively.
  
* Setup a CloudFront distribution to disrtibute the Website 

* Access the website through a web browser 
