---
layout: post
title:  "Blog Hosting"
categories: programming
tags: programming blog hosting s3 aws cloudfront route53
---

### Hosting this Blog
This blog is staticly hosted on an [S3 bucket](https://aws.amazon.com/s3/) in [AWS](https://aws.amazon.com/).
S3 is a block store service that also allows hosting of static sites with HTTP. 
I've registered the jamesfheath.com domain with [Route53](https://aws.amazon.com/route53/), AWS's DNS service. 
My first attempt at hosting was to simply point an [Alias](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-choosing-alias-non-alias.html) record in Route53 that pointed to the S3 bucket. 
The bucket is also named jamesfheath.com, which is a requirement for custom domain name hosting. 

### Using CloudFront to Implement HTTPs
I quickly moved away from the S3 diret hosting and towards [CloudFront](https://aws.amazon.com/cloudfront/), AWS's content deliver network, so that I could use HTTPs.
First I needed to create a [public certificate](https://en.wikipedia.org/wiki/Public_key_certificate), which I did with [AWS Certificate Manager](https://aws.amazon.com/certificate-manager/).
This involved verifying my identity, but was automated by AWS because I am using Route53 as my domain registrar. 
Creating a CloudFront distribution was the next step, which I then pointed to my S3 bucket (now private and NOT hosting enabled).
The final step was to go to Route53 and create an alias record that pointed to the CloudFront distribution.
And that's it!



