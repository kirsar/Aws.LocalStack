# Aws.LocalStack

Docker configuration for [localstack](https://github.com/localstack/localstack) to host AWS services locally

To run the container:
docker pull localstack/locastack
docker-compose up -d

watch running services
http://localhost:8055/#!/infra

init SQS and SNS with AWS CLI

Create Topic:
```
$ aws --endpoint-url=http://localhost:4575 sns create-topic --name my_topic
```
List Topic:
```
$ aws --endpoint-url=http://localhost:4575 sns list-topics
```
Subscribe Queue to Topic:
```
$ aws --endpoint-url=http://localhost:4575 sns subscribe --topic-arn arn:aws:sns:us-east-1:123456789012:my_topic --protocol sqs --notification-endpoint arn:aws:sns:us-east-1:123456789012:my_queue
```
List subscriptions:
```
$ aws --endpoint-url=http://localhost:4575 sns list-subscriptions
```
Create Queue:
```
$ aws --endpoint-url=http://localhost:4576 sqs create-queue --queue-name my_queue
```
List Queue:
```
$ aws --endpoint-url=http://localhost:4576 sqs list-queues
```
