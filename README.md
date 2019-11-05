# AWS-CloudWatch-CustomMerrics

The default metric collection includes CPU Utilisation, Network Traffic and Disk Read/Writes. It does not include metrics to monitor Disk Space and Memory Usage. Hence, we are in the need of custom metrics if we want to monitor the Memory (RAM) usage and Disk space, of our instances.

In order to implement the cloud watch custom metrics in your existing Beanstalk Environment, please follow the following steps,

Prerequisites:-
1. Elastic Beanstalk Environment with an application running on it.
2. You should have a IAM user with full Administrator Access.

Steps to implement custom metrics

Copy the file "EBcustomMetrics.config" and paste it under the ".ebextension" folder. If you don't have ".ebextension" folder go ahead and create it in the root of your application code.

Deploy the code to your environment.

The Custom Metrics can be viewed under
Cloudwatch -> Metrics -> Linux System

InstanceId section will give you the Memory utilisation metrics (RAM) for each individual instances in your environment.

AutoScalingGroupName section will give you the Average Memory utilisation metrics (RAM) for your environment.

Filesystem section will give you the Disk utilisation metrics for each individual instances in your environment.

AutoScalingGroupName Filesystem section will give you the Average Disk utilisation for your environment.
