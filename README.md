# SQS Write Stream
Create a writable stream to send your SQS messages.

## Requirements
Requires Node 8.0 or greater

## Additional Stream Events
```
const SqsWriteStream = require('sqs-write-stream');
const rs = new  SqsWriteStream(queueUrl, options);

rs.on('streamConstructed',
    (queueUrl, options) => console.info(queueUrl, options));

rs.on('msgReceived', msg => console.info(msg));

rs.on('msgProcessed', msg => console.info(msg));

rs.on('msgProcessingErr', console.error(obj, err));

rs.on('streamFinishingErr', err => console.error(err));