---
layout: post
title:  "AWS: Configure Cloudwatch Agent for Logging on EC2 with Cloudformation Template"
categories: programming
tags: aws cloudwatch agent ec2 cloudformation template logging
---

### Setting up Cloudwatch Agent on EC2 Using Cloudformation Template
Setting up a Cloudwatch Agent on EC2 allows you to log files locally on your EC2 and have the Cloudwatch Agent send them to a specified Cloudwatch Group.
The Cloudwatch Agent can also send other metrics about your instance, but I'm going to focus on the logging aspect.  
I found that setting it up using Cloudformation templates (CFTs) following the [AWS Guides](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent-New-Instances-CloudFormation.html) was a little complicated and I wanted to boil it down and give a straightforward example. 

### Creating our Cloudformation Template
[This CFT](https://github.com/JamesFHeath/jamesfheathblog_code/blob/master/AWS/CloudwatchAgentEC2Logging.template) contains an [AutoScaling Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-as-group.html) for our EC2 instances and a startup script that will automatically install and run our Cloudwatch Agent on EC2 startup using the *userdata* section.
The Cloudwatch Agent [configuration file](https://github.com/JamesFHeath/jamesfheathblog_code/blob/master/AWS/CloudWatchAgentConfig.json) will be stored and in and read from S3.
The configuration will allow us to write logs to a directory on EC2 and have them appear in Cloudwatch. 
This template is modelled on the [AWS sample template](https://github.com/awslabs/aws-cloudformation-templates/blob/master/aws/solutions/AmazonCloudWatchAgent/inline/amazon_linux.template) and uses Amazon Linux. 
Besides the boilerplate, you just need to configure the S3 Bucket the Cloudwatch config file is in. 


### Cloudwatch Configuration File
We're just creating a basic configuration file for logging.
Anything we log on our EC2 instance to /opt/aws/amazon-cloudwatch-agent/logs/*.log will be outputted in Cloudwatch under log group test.log and log stream test.log.
Put this config file into your desired S3 location. 
{% highlight json %}
{
    "agent": {
        "metrics_collection_interval": 10,
        "logfile": "/opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log"
    },
    "logs": {
        "logs_collected": {
            "files": {
                "collect_list": [
                    {
                        "file_path": "/opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log",
                        "log_group_name": "amazon-cloudwatch-agent.log",
                        "log_stream_name": "amazon-cloudwatch-agent.log",
                        "timezone": "UTC"
                    },
                    {
                        "file_path": "/opt/aws/amazon-cloudwatch-agent/logs/*.log",
                        "log_group_name": "test.log",
                        "log_stream_name": "test.log",
                        "timezone": "Local"
                    }
                ]
            }
        }
    }
}
{% endhighlight %}


### Testing
Create your Cloudformation stack and spin up an EC2 instance. 
Because we've put a log file into /opt/aws/amazon-cloudwatch-agent/logs/*.log it should show up with "testlog" in Cloudwatch after some Cloudwatch Agent default output. 

![Cloudwatch Log](/images/CloudwatchLog.png)