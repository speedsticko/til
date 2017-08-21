My AWS Lambda Learning Page
===========================

Purpose: Run code when an event happens.

Problem: I want to do something when ever an event happens. 

Old Way: Set up a service bus (SQS for AWS), write code to emit the event to the queue, write app to listen to queue and respond to the events of interest. As you can see there is a lot of compute resources to create, run, and manage.

Solution: With AWS Lambda, you choose from the available events, write you event handling code, and that's it.

How is this different from Amazon Elastic Beanstalk or EC2, EC2 Container service?
- everything is managed for your function

You can also have scheduled tasks with AWS Lambda.
Things like logging and monitoring are provided through CloudWatch.

How is AWS Lambda charged?
What are good use cases for Lambda?
