# Monitoring AWS Elemental MediaPackage with Amazon CloudWatch Events<a name="monitoring-cloudwatch-events"></a>

Amazon CloudWatch Events enable you to automate your AWS services and respond automatically to system events such as application availability issues or error conditions\. AWS services deliver events to CloudWatch Events in near real\-time\. You can write simple rules to indicate which events are of interest to you, and what automated actions to take when an event matches a rule\. The actions that can be automatically triggered include the following:
+ Invoking an AWS Lambda function
+ Invoking Amazon EC2 Run Command
+ Relaying the event to Amazon Kinesis Data Streams
+ Activating an AWS Step Functions state machine

An example of using CloudWatch Events with AWS Elemental MediaPackage is notifying an Amazon SNS topic if you reach the maximum stream ingest\.

For more information about creating rules in CloudWatch Events, see the [Amazon CloudWatch Events User Guide](http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/)\.

For a list of events that AWS Elemental MediaPackage emits, see [AWS Elemental MediaPackage Events](cloudwatch-events-example.md)\.