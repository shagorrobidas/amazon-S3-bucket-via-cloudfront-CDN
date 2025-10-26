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

#### We have to paste above Cloud front distribution policy to S3 bucket policy
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/21.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>


#### Click on edit button and paste the copied policy and click on save changes
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/22.webp?raw=true" alt="Amazon S3 with CloudFront">
</p>

#### Now let’s upload an text file to our bucket and try to see it’s content by cloudfront CDN
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/23.webp?raw=true" alt="Uploading file to S3">
</p>

#### Select file and click on upload button
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/24.webp?raw=true" alt="Uploading file to S3 bucket">
</p>

#### After file uploading we will be redirected to list file page
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/25.webp?raw=true" alt="Uploaded files list page">
</p>

#### Click on a.txt to open file details
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/26.webp?raw=true" alt="Getting deatils of a S3 object">
</p>

#### Now open object URL in new tab, then you will get something like Access Denied because our S3 bucket is private
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/27.webp?raw=true" alt="Getting access denied becaue bucket is private">
</p>

#### Now Let’s replace S3 base URL by cloudfront distribution name.
#### here we are able to see the S3 bucket content because we have added cloudfront policy in S3 bucket policy.
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/28.webp?raw=true" alt="Access S3 private file access by cloudfront distribution domain name">
</p>

  ## Now Let’s Implement that in Django code base
  Make sure to install and add these dependencies to your ```requirements.txt``` :

```
  Django==4.2.15
  django-storages==1.14.4
  boto3==1.35.10
  python-decouple==3.8
```
  
#### Create a file storage_backends.py next to your settings.py file and put below code in it:
```
  from django.conf import settings
  from storages.backends.s3boto3 import S3Boto3Storage
  
  
  class StaticStorage(S3Boto3Storage):
      location = 'staticfiles'
  
  class PublicMediaStorage(S3Boto3Storage):
      location = 'media'
      file_overwrite = False
```

####  In settings.py
```
  USE_S3 = True
  
  if USE_S3:
      # aws settings
      AWS_ACCESS_KEY_ID = config('AWS_ACCESS_KEY_ID')
      AWS_SECRET_ACCESS_KEY = config('AWS_SECRET_ACCESS_KEY')
      AWS_STORAGE_BUCKET_NAME = config('AWS_STORAGE_BUCKET_NAME')
      AWS_S3_REGION_NAME = "us-east-1"
      AWS_S3_CUSTOM_DOMAIN = f'https://{AWS_STORAGE_BUCKET_NAME}.s3.amazonaws.com'
      CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME = config('CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME', default=None)
      AWS_S3_OBJECT_PARAMETERS = {'CacheControl': 'max-age=86400'}
  
      if CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME:
          AWS_S3_CUSTOM_DOMAIN = CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME
  
      # s3 static settings
      AWS_LOCATION = 'staticfiles'
      STATIC_URL = f'{AWS_S3_CUSTOM_DOMAIN}/{AWS_LOCATION}/'
      STATICFILES_STORAGE = 'Smart_blogging_system.storage_backends.StaticStorage'
      # STATICFILES_STORAGE = 'storages.backends.s3boto3.S3Boto3Storage'
      
      # s3 public media settings
      PUBLIC_MEDIA_LOCATION = 'media'
      MEDIA_URL = f'{AWS_S3_CUSTOM_DOMAIN}/{PUBLIC_MEDIA_LOCATION}/'
      DEFAULT_FILE_STORAGE = 'Smart_blogging_system.storage_backends.PublicMediaStorage'
  else:
      STATIC_URL = '/staticfiles/'
      STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
  
      MEDIA_URL = '/media/'
      MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```


#### Set below variable in your .env file with their accurate value. below i have provided some dummy values

````
AWS_ACCESS_KEY_ID="AWS IAM USER ACCESS_KEY_ID"
AWS_SECRET_ACCESS_KEY="AWS IAM USER SECRET_ACCESS_KEY"
AWS_STORAGE_BUCKET_NAME="AWS s3 BUCKET NAME"
CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME="CLOUDFRONT_DISTRIBUTION_DOMAIN_NAME without https://"
````

#### After that we have to run
``` python3 manage.py collectstatic ```

#### after running collectstatic command all the files will be uploaded to S3

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/29.webp?raw=true" alt="uploading static files to S3 by collect static command">
</p>

#### Let’s open Django default admin panel, and you will be able to see that our static files are getting loaded from cloudfront

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/30.webp?raw=true" alt="static files loading from cloudfront">
</p>


#### In the Normal user UI also we can see that media files are also getting loaded from cloudfront.


<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/31.webp?raw=true" alt="static files loading from cloudfront">
</p>


### Now let’s understand the concept of cache Invalidation in cloudfront CDN
<p><strong> Let’s change our base.html body background color to greenyellow and see whether our changes are getting reflected or not. </strong></p>

<p>I have changed base.css but still back-ground color is coming as yellow. i have uploaded the updated base.css file on S3 also. Still our changes are not getting reflected. for getting updated changes we will have to create cache invalidation.</p>

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/32.webp?raw=true" alt="Creating cache invalidation"><br>
  <span style="font-size:11px;">Creating cache invalidation</span>
</p>

### here we have specified the pattern to Invalidate everything

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/33.webp?raw=true" alt="Creating cache invalidation"><br>
  <span style="font-size:11px;">Creating cache invalidation</span>
</p>

### After completion of our cache Invalidation we will be able to see updated css code

<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/34.webp?raw=true" alt="Creating cache invalidation"><br>
  <span style="font-size:11px;">Applying regex for cache invalidation</span>
</p>

### Old base.css file
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/34.webp?raw=true" alt="Creating cache invalidation"><br>
  <span style="font-size:11px;">static file by cloudfront cache invalidation concept</span>
</p>


### Updated base.css file
<p align="center">
  <img src="https://github.com/shagorrobidas/amazon-S3-bucket-via-cloudfront-CDN/blob/main/image/34.webp?raw=true" alt="Creating cache invalidation"><br>
  <span style="font-size:11px;">updated static file by cloudfront cache invalidation concept</span>
</p>

## Conclusion
<p>
  Finally, We have successfully configured S3 and Cloud front to server our django static and media fields.
</p>

