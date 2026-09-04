
# EXPERIMENT 5
## AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL

### Objective

To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.

### 1. Requirements

- AWS Account
- Web Browser
- Internet Connection
- Amazon S3 access
- AWS CloudTrail

---

## PART A — ACCESS AWS CLOUDTRAIL

### Step 1: Login to AWS

1. Open the AWS Management Console.
2. Sign in using your AWS account.
3. In the AWS search bar, type CloudTrail.
4. Select AWS CloudTrail.

**Screenshot 1:** AWS CloudTrail dashboard.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/30b5ea72-1cb8-4732-9c36-0b1f5bc545fc" />


### Step 2: Open Event History

1. In the CloudTrail navigation menu, select Event history.
2. CloudTrail displays recent AWS activity.
3. Review the available events.

The Event History page may display:

- Event time
- Username
- Event name
- Event source
- Resource type
- Resource name

**Screenshot 2:** CloudTrail Event History.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/88320537-e5bf-4767-a150-c52b64f74227" />


---

## PART B — ANALYZE A CLOUDTRAIL EVENT

### Step 3: Select an Event

1. From the Event History list, select an S3-related event.
2. Click the event to open its details.
3. Examine the event information and the event record/JSON.

For this experiment, a CreateBucket event can be used.

### Step 4: Analyze the CreateBucket Event

The CreateBucket event indicates that an Amazon S3 bucket creation operation was attempted.

| Parameter | Observation |
|---|---|
| Event Time | 2026-08-06 12:10:55 UTC |
| User Name | Root |
| Event Name | CreateBucket |
| Event Source | s3.amazonaws.com |
| AWS Region | ap-south-1 |
| Read-only | false |
| Error Code | BucketAlreadyExists |
| Activity | S3 bucket creation |

**Screenshot 3:** CreateBucket event details.

### Meaning of Important Fields

| Field | Meaning |
|---|---|
| Event Time | Time at which the activity occurred |
| User Name | User/identity associated with the activity |
| Event Name | AWS operation that was performed |
| Event Source | AWS service that generated the event |
| AWS Region | Region where the activity occurred |
| Read-only | Indicates whether the event was only a read operation or involved a change |
| Error Code | Indicates whether an error occurred |

---

## PART C — IDENTIFY ANOTHER CLOUDTRAIL EVENT

### Step 5: Select Another Event

1. Return to CloudTrail → Event history.
2. Select another event.
3. Open its details.
4. Record the important fields.

For example, an event such as AutomatedDefaultVpcCreation may be present.

This event is associated with Amazon EC2.

### Step 6: Analyze the Second Event

| Parameter | Observation |
|---|---|
| Event Time | 2026-08-06 14:13:24 UTC |
| User Name | EC2 service (ec2.amazonaws.com) |
| Event Name | AutomatedDefaultVpcCreation |
| Event Source | ec2.amazonaws.com |
| AWS Region | ap-south-1 |
| Read-only | false |
| Error Code | None |
| Activity | Automated default VPC creation |

**Screenshot 4:** Second CloudTrail event details.

---

## PART D — COMPARE THE EVENTS

### Step 7: Prepare the Audit Comparison

| Parameter | Event 1 | Event 2 |
|---|---|---|
| Event Time | 2026-08-06 12:10:55 UTC | 2026-08-06 14:13:24 UTC |
| User Name | Root | EC2 service (ec2.amazonaws.com) |
| Event Name | CreateBucket | AutomatedDefaultVpcCreation |
| Event Source | s3.amazonaws.com | ec2.amazonaws.com |
| AWS Region | ap-south-1 | ap-south-1 |
| Read-only | false | false |
| Error Code | BucketAlreadyExists | None |
| Activity | S3 bucket creation | Automated VPC creation |

### Comparison of the Two Events

| Aspect | Event 1 | Event 2 |
|---|---|---|
| Service | Amazon S3 | Amazon EC2 |
| Purpose | Attempted to create an S3 bucket | Automatically created a default VPC |
| Initiated by | Root user | EC2 service |
| Result | Failed because the bucket name was already taken | Successful; no error code was recorded |
| Time | 12:10:55 UTC | 14:13:24 UTC |
| Region | ap-south-1 | ap-south-1 |
| Read-only | false | false |

**Conclusion:** Event 1 was a failed S3 bucket creation attempt, while Event 2 was a successful automatic VPC creation by the EC2 service. Both occurred in the same AWS region.

---

## PART E — SECURITY AUDIT ANALYSIS

### Step 8: Identify Who, What, When and Where

| Audit Question | Event 1 — CreateBucket | Event 2 — AutomatedDefaultVpcCreation |
|---|---|---|
| WHO? | Root user | EC2 service |
| WHAT? | S3 bucket creation attempt | Automated default VPC creation |
| WHEN? | 2026-08-06 12:10:55 UTC | 2026-08-06 14:13:24 UTC |
| WHERE? | ap-south-1 | ap-south-1 |
| RESULT? | Failed — BucketAlreadyExists | Successful — No error code |

### Step 9: Prepare the Final Audit Table

| Event Time | User | Event Name | Service | Region | Read-only | Result | Activity |
|---|---|---|---|---|---|---|---|
| 2026-08-06 12:10:55 UTC | Root | CreateBucket | Amazon S3 | ap-south-1 | false | Failed — BucketAlreadyExists | S3 bucket creation |
| 2026-08-06 14:13:24 UTC | EC2 service (ec2.amazonaws.com) | AutomatedDefaultVpcCreation | Amazon EC2 | ap-south-1 | false | Successful — No error code | Automated VPC creation |

---

## PART F — SCREENSHOTS TO SUBMIT

1. AWS CloudTrail Dashboard
2. CloudTrail Event History
3. CreateBucket Event Details
4. Second CloudTrail Event Details
5. Final Audit/Observation Table

---

## RESULT

The cloud activities in AWS were successfully audited using AWS CloudTrail Event History. Different AWS events were examined based on event time, user identity, event name, event source, AWS Region, read-only status, and error status. The experiment demonstrated how AWS CloudTrail provides an audit trail for monitoring, accountability, and investigation of cloud activities.
