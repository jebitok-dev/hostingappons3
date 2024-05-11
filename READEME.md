## Hosting Static HTML Website on S3 Bucket

In this project I hosted a static website on a S3 Bucket

### Static Website Endpoint 
[SimpleApp endpoint](http://simple1appbucket.s3-website.eu-north-1.amazonaws.com)

## Steps 
### Create a bucket
- On [AWS Console](https://aws.amazon.com/s3/) select s3 and name the bucket then create bucket

### Enabling the static website hosting 
On Bucket list choose properties and edit the static website hosting:
- Choose use this bucket to host a website
- enable the static website hosting 

On the Index Document 
- enter file name index.html and error.html 
- save the changes 

Copy the Static Website hosting endpoint 
- [Endpoint](http://simple1appbucket.s3-website.eu-north-1.amazonaws.com)

### Edit Block Public Access Settings 
Choose Permissions then edit the Block Public Access (Bucket Settings)
- Block all public access and save changes 

### Add Bucket policy that makes your bucket content publicly available 
Choose Permission then edit the Bucket Policy 
- Grant public read access for your website 

``````
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::simple1appbucket/*"
            ]
        }
    ]
}
``````

### Configure HTML and Error Document locally
- Configure the files for the static app locally it could have images 
- upload the files (HTML files and images) using drag and drop into uploading documents section of enabling website hosting 


### Test your website endpoint 
- [Bucket website endpoint](http://simple1appbucket.s3-website.eu-north-1.amazonaws.com)


## Acknowledgement 

I want to acknowledge instructors at [ALTSchool Africa](https://altschoolafrica.com) and the [AWS](https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html) for the resources and guide on how to host a static website successfully
