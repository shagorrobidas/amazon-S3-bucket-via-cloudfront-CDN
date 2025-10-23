# Serving Django Static and Media Files from a Private Amazon S3 Bucket via CloudFront CDN

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/1.webp?raw=true" alt="Amazon S3 with CloudFront" width="600">
</p>

## What would you learn?
#### **You will be able to understand the below topics in detail with practical screenshots**
- How to configure private S3 bucket and Cloud front to server our django static and media fields.
- We will configure our S3 Private bucket for serving static and media files for improving security.
- Images and files will load very fast because of cloudfront cdn.


### Create AWS S3 Bucket for Django static and media files upload
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/2.webp?raw=true" alt="Amazon S3 with CloudFront" >
</p>

### Provide bucket name and disable ACL

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/3.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Click on block all public access for making our S3 bucket private and more secure

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/4.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Scroll down and click on “Create bucket” button.
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/5.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Create an IAM user
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/6.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Click on Create user
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/7.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Give your new user a name, and let it be unchecked only “Provide user access to AWS Management Console” and click “Next”
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/8.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Select “Attach policies directly” and search for AmazonS3FullAccess
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/9.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Click the “Create user” button
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/10.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### You will be taken to the list of all users. Find your new user, click on it.
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/11.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Click on “Security credentials” tab
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/12.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Select “Command Like Interface (CLI)”, check that I understand the above recommendations and click “Next”
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/13.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Click the button “Create access key” and copy your Access key and Secret access key
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/14.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

### Now we need to Configure CloudFront CDN for serving Django static and media files from S3 private bucket

#### Click on “Create distribution”
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/15.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### Click on “Origin Domain” and select your bucket:
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/16.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### Select Origin access control settings (recommended) and click on create new OAC
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/17.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### Give any name and click on Create
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/18.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### select Do not enable security protections ( for production use case we can go with with “Enable security protections )
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/19.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### Scroll down and click on create distribution button
#### Copy “Distribution domain name” and “copy policy”
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/20.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>
