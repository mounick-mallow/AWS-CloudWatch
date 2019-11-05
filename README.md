# AWS-CloudWatch-CustomMerrics

The default metric collection includes CPU Utilisation, Network Traffic and Disk Read/Writes. It does not include metrics to monitor Disk Space and Memory Usage. Hence, we are in the need of custom metrics if we want to monitor the Memory (RAM) usage and Disk space, of our instances.

In order to implement the cloud watch custom metrics in your existing Beanstalk Environment, please follow the following steps,

Prerequisites:-
1. Elastic Beanstalk Environment with an application running on it.
2. You should have a IAM user with full Administrator Access.

Steps to implement custom metrics

In IAM console choose roles and select aws-elasticbeanstalk-ec2-role and click Attach policy, search for AWS managed policy named “CloudWatchAgentServerPolicy” and attach with this role.

Add the file “cloudwatch.config”  in your codebase under “.ebextension” folder. So the file structure will be look like (/ .ebextension / cloudwatch.config). If you don’t have “.ebextension” folder go ahead and create it, in the root of your application source code.

Add the following contents in your folder. 
