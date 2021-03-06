# Packager Settings Fields<a name="endpoints-dash-packager"></a>

1. For **Type**, choose **DASH\-ISO**\.

1. \(Optional\) For **Segment duration**, type the duration \(in seconds\) of each segment\. If the value that you type here is different from the input segment size, AWS Elemental MediaPackage rounds segments to the nearest multiple of the input segment duration\.

1. \(Optional\) For **Manifest window duration**, type the total duration \(in seconds\) of the manifest\.

1. \(Optional\) In **Profile**, specify a DASH profile, like HbbTV\.

   Choose from the following:
   + **None** – the output doesn't use a DASH profile
   + **Hbbtv 1\.5** – the output is HbbTV\-compliant

1. \(Optional\) For **Min update period**, type the minimum amount of time \(in seconds\) that the player should wait before requesting manifest updates\. A lower value means that manifests are updated more frequently, but a lower value also contributes to request and response network traffic\.

1. \(Optional\) For **Min buffer time**, type the minimum amount of time \(in seconds\) that a player must keep in the buffer\. If network conditions interrupt playback, the player will have additional buffered content before playback fails, allowing for recovery time before the viewer's experience is affected\.

1. \(Optional\) For **Suggested presentation delay**, enter the amount of time \(in seconds\) that the player should be from the end of the manifest\. This sets the content start point back x seconds from the end of the manifest \(the point where content is live\)\. For example, with a 35\-second presentation delay, requests at 5:30 receive content from 5:29:25\. When used with time delay, AWS Elemental MediaPackage adds the suggested presentation delay to the time delay duration\.

1. For **Period triggers**, choose how AWS Elemental MediaPackage creates media presentation description \(MPD\) periods in the DASH output manifest\. Choose from the following:
   + **None** – AWS Elemental MediaPackage doesn't create additional periods\. It formats the manifest as a single period and doesn't include SCTE\-35 markers in the segments\.
   + **Trigger new periods on ads** – AWS Elemental MediaPackage creates and inserts in the manifest multiple periods based on SCTE\-35 ad markers from the input content\. These periods separate portions of the content, such as setting boundaries between the main content and ad content\. For more information about how AWS Elemental MediaPackage configures periods in the manifest, see [Multi\-period DASH in AWS Elemental MediaPackage](multi-period.md)\.
**Important**  
Multiple periods are required if you use AWS Elemental MediaTailor for personalized ad insertion in DASH content\. For more information about this service, see the [AWS Elemental MediaTailor User Guide](http://http://docs.aws.amazon.com/mediatailor/latest/ug/)\.