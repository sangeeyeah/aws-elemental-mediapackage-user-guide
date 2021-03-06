# How AWS Elemental MediaPackage Works<a name="what-is-flow"></a>

AWS Elemental MediaPackage uses just\-in\-time format conversion to deliver over\-the\-top \(OTT\) video from a single source to a wide variety of playback devices or content delivery networks \(CDNs\)\.

Here is the general processing flow:

1. An upstream encoder \(such as AWS Elemental MediaLive\) sends an HLS live stream over WebDAV to the AWS Elemental MediaPackage channel ingest URL, and includes the channel's access credentials \(as supplied in MediaPackage\)\. If you're using input redundancy, the encoder sends two identical HLS live streams to MediaPackage, one to each ingest URL on the channel\. MediaPackage uses the stream from one ingest URL as the source content\. If MediaPackage stops receiving content on the active ingest URL, it automatically switches to the other ingest URL for source content\. Additionally, AWS scales resources up and down to handle the incoming traffic\.

   For more information, see [How Input Redundancy Works](what-is-flow-ir.md)\.

1. A downstream device requests content from AWS Elemental MediaPackage through the endpoint egress URL\. A downstream device is either a video player or a content distribution network \(CDN\)\. The egress URL is associated with an endpoint for a specific streaming format \(either Apple HLS, DASH\-ISO, CMAF, or Microsoft Smooth Streaming\)\.

1. When AWS Elemental MediaPackage receives the playback request from the downstream device, it dynamically packages the stream according to the settings that you specified on the endpoint\. Packaging can include adding encryption and configuring audio, video, and subtitles or captions track outputs\.

1. AWS Elemental MediaPackage delivers the output stream over HTTPS to the requesting device\. As with ingest, AWS scales resources up and down to handle changes in traffic\.

1. AWS Elemental MediaPackage logs activity through Amazon CloudWatch\. You can view information like the number of content requests and ingress or egress bytes\. For information about viewing MediaPackage metrics in CloudWatch, see [Monitoring AWS Elemental MediaPackage with Amazon CloudWatch](monitoring-cloudwatch.md)\.

Throughout the ingest and egress processes, AWS Elemental MediaPackage detects and mitigates potential infrastructure failures before they become a problem for viewers\. 

The following illustration shows the overall process\.

![\[AWS Elemental MediaPackage workflow\]](http://docs.aws.amazon.com/mediapackage/latest/ug/images/bbl flow1.png)