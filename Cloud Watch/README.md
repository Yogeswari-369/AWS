AWS CloudWatch is a powerful monitoring and observability service provided by Amazon Web Services. 
CloudWatch collects and tracks metrics, collects and monitors log files, and sets alarms to alert you on certain conditions.



++++ Default_Metrics +++++

This python script increase and decrease the CPU utilization on the EC2 instance. By using Cloud Watch we can track those metrics.
Once it exceeds the specified limitation, it triggers the alarm and notified the issue by the email.


We can monitoring the CPU utiization under Cloud Watch ---> Metrics ---> select an instanced based on the instance_id
And for Alarm configuration, we have to follow these steps.

Step 1: Specify Metric and condtion
           Here, I choose Metric as EC2 instance and select either per_instance or across all the instances. Select the instance based 
           on the instance_id. And the condition is CPU utilization exceeds >= 50 and statistic time as Average and period of time is 5 minute
	   
Step 2 : Configure action
	        Sending notification via SNS(simple notification service) / create topic / ARN topic
	        In create topic, provide the email
	 
Step 3 : Add name & Description
      	  Provide alarm name & write some description about the alarm
	 
Step 4 : Preview & create


![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/a88aa399-45d6-4fb4-bd16-9f201957e3d8)
![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/3387e657-89ff-48ab-856b-a9e08afb7591)
![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/f591b431-6859-4c6e-8c6f-e1da3a905ce2)
![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/93fde424-c0b2-40c2-aa3d-aac6c1e932aa)


