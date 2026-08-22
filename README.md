EXPERIMENT 5
AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL
Objective
To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.
1. Requirements
•	AWS Account 
•	Web Browser 
•	Internet Connection 
•	Amazon S3 access 
•	AWS CloudTrail 

PART A — ACCESS AWS CLOUDTRAIL
Step 1: Login to AWS
1.	Open the AWS Management Console. 
2.	Sign in using your AWS account. 
3.	In the AWS search bar, type CloudTrail. 
4.	Select AWS CloudTrail. 
Screenshot 1: AWS CloudTrail dashboard.

Step 2: Open Event History
1.	In the CloudTrail navigation menu, select Event history. 
2.	CloudTrail displays recent AWS activity. 
3.	Review the available events. 
The Event History page may display information such as:
•	Event time 
•	Username 
•	Event name 
•	Event source 
•	Resource type 
•	Resource name 
Screenshot 2: CloudTrail Event History.

PART B — ANALYZE A CLOUDTRAIL EVENT
Step 3: Select an Event
1.	From the Event History list, select an S3-related event. 
2.	Click the event to open its details. 
3.	Examine the event information and the event record/JSON. 
For this experiment, a CreateBucket event can be used.
Step 4: Analyze the CreateBucket Event
The CreateBucket event indicates that an Amazon S3 bucket creation operation occurred.
Record the following information:
Parameter	Observation
Event Time	__________
User Name	__________
Event Name	CreateBucket
Event Source	s3.amazonaws.com
AWS Region	__________
Read-only	__________
Error Code	__________
Activity	S3 bucket creation

Meaning of Important Fields
Field	Meaning
Event Time	Time at which the activity occurred
User Name	User/identity associated with the activity
Event Name	AWS operation that was performed
Event Source	AWS service that generated the event
AWS Region	Region where the activity occurred
Read-only	Indicates whether the event was only a read operation or involved a change
Error Code	Indicates whether an error occurred

Screenshot 3: CreateBucket event details.
PART C — IDENTIFY ANOTHER CLOUDTRAIL EVENT
Step 5: Select Another Event
1.	Return to CloudTrail → Event history. 
2.	Select another event. 
3.	Open its details. 
4.	Record the important fields. 
For example, an event such as:
AutomatedDefaultVpcCreation
may be present.
This event is associated with Amazon EC2.
Step 6: Analyze the Second Event
Record:
Parameter	Observation
Event Time	__________
User Name	__________
Event Name	AutomatedDefaultVpcCreation
Event Source	ec2.amazonaws.com
AWS Region	__________
Read-only	__________
Error Code	__________
Activity	Automated default VPC creation
Screenshot 4: Second CloudTrail event details.
PART D — COMPARE THE EVENTS
Step 7: Prepare the Audit Comparison
Compare the two CloudTrail events.
Parameter	Event 1	Event 2
Event Time	__________	__________
User Name	__________	__________
Event Name	CreateBucket	AutomatedDefaultVpcCreation
Event Source	s3.amazonaws.com	ec2.amazonaws.com
AWS Region	__________	__________
Read-only	__________	__________
Error Code	__________	__________
Activity	S3 bucket creation	Automated VPC creation

PART E — SECURITY AUDIT ANALYSIS
Step 8: Identify Who, What, When and Where
For each event, identify:
WHO?
Who or which identity performed/generated the activity?
WHAT?
What AWS operation was performed?
WHEN?
At what date and time did the activity occur?
WHERE?
In which AWS Region did the activity occur?
RESULT?
Was the operation successful or did it generate an error?
Step 9: Prepare the Final Audit Table
Students should prepare a final table similar to the following:
Event Time	User	Event Name	Service	Region	Read-only	Result	Activity
__________	__________	CreateBucket	Amazon S3	__________	__________	__________	S3 bucket creation
__________	__________	AutomatedDefaultVpcCreation	Amazon EC2	__________	__________	__________	Automated VPC creation

PART F — SCREENSHOTS TO SUBMIT
Students should capture the following screenshots:
1.	AWS CloudTrail Dashboard 
2.	CloudTrail Event History 
3.	CreateBucket Event Details 
4.	Second CloudTrail Event Details 
5.	Final Audit/Observation Table
RESULT
The cloud activities in AWS were successfully audited using AWS CloudTrail Event History. Different AWS events were examined based on event time, user identity, event name, event source, AWS Region, read-only status, and error status. The experiment demonstrated how AWS CloudTrail provides an audit trail for monitoring, accountability, and investigation of cloud activities.
