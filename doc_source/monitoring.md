# Monitoring AWS Elemental MediaPackage<a name="monitoring"></a>

Monitoring is an important part of maintaining the reliability, availability, and performance of AWS Elemental MediaPackage and your other AWS solutions\. AWS provides the following monitoring tools to watch MediaPackage, report when something is wrong, and take automatic actions when appropriate:
+ *Amazon CloudWatch* monitors your AWS resources and the applications that you run on AWS in real\-time\. You can collect and track metrics, create customized dashboards, and set alarms that notify you or take actions when a specified metric reaches a threshold that you specify\. For example, you can have CloudWatch track CPU usage or other metrics of your Amazon EC2 instances and automatically launch new instances when needed\. For more information, see the [Amazon CloudWatch User Guide](http://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/)\.
+ *Amazon CloudWatch Events* delivers a near real\-time stream of system events that describe changes in AWS resources\. CloudWatch Events enables automated event\-driven computing, as you can write rules that watch for certain events and trigger automated actions in other AWS services when these events happen\. For more information, see the [Amazon CloudWatch Events User Guide](http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/)\.

**Topics**
+ [Monitoring AWS Elemental MediaPackage with Amazon CloudWatch](monitoring-cloudwatch.md)
+ [Monitoring AWS Elemental MediaPackage with Amazon CloudWatch Events](monitoring-cloudwatch-events.md)