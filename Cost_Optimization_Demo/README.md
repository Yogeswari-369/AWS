Create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.


- The Lambda function fetches all EBS snapshots and also retrieves a list of active EC2 instances (running and stopped).
- For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/13ae5bf9-c16f-45ca-89f1-a43bd2ac4b3d)

Reference : https://boto3.amazonaws.com/v1/documentation/api/1.9.42/reference/services/ec2.html
