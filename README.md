# A Python module for creating sample events to test AWS Lambda functions.
This small module is meant to help test Python based [AWS Lambda](https://aws.amazon.com/lambda/) functions that get triggered by other AWS services (ex: CodePipeline action).  The module will generate an "event" that appears to come from a specified service which can be used to simulate an actual invocation of the function.

# Installation
``` pip install aws_lambda_sample_events ```

# Usage Example
```python
from aws_lambda_sample_events import SampleEvent
from pprint import pprint
codepipeline = SampleEvent('codepipeline')
pprint(codepipeline.event)
```
`SampleEvent()` expects a single string argument representing the name of the AWS Service you would like a sample event for.  

## Valid arguments, and supported services, are:
* codepipeline
* sns
* cloudformation
* ses
* scheduled
* dynamodb_update
* cognito_sync_trigger
* kinesis_stream
* s3_put
* s3_delete
* cloudwatch_logs
* cloudwatch_events
* config_rule
