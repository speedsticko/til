My AWS Lambda Learning Page
===========================

Purpose: Run code when an event happens.

Problem: I want to do something when ever an event happens. 

Old Way: Set up a service bus (SQS for AWS), write code to emit the event to the queue, write app to listen to queue and respond to the events of interst.

