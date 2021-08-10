# aws_sam_py_sqs_receiver
Amazon SQS Receiver Template and Lambda handler with AWS SAM

# Template

The SAM template performs the following:
1. Creates a SQS resource with name MySqsQueue
2. Creates an event MySQSEvent which listens to MySqsQueue with a batch size of 10
3. Specifies event handler as ```process_sqs_records.lambda_handler``` 

# Functionality

The lambda handler simply prints the _body_ of SQS payload

# Build Status

[![CircleCI](https://circleci.com/gh/jeyabalajis/aws_sam_py_sqs_receiver/tree/master.svg?style=svg)](https://circleci.com/gh/jeyabalajis/aws_sam_py_sqs_receiver/tree/master)

# Workflow

## Local Invoke
```
sam local invoke --event ./event/event.jsonsam local invoke --event ./event/event.json
```

You should see the following output in the terminal:
```
test
Hello from SQS!
```

## Build

```sam build```

## Deploy

```sam deploy```

> Ensure that ```confirm_changeset = false``` under samconfig.toml

> You can also set other default deploy parameters under samconfig.toml

