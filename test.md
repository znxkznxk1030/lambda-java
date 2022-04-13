```bash
mvn build

aws s3 cp ./target/demo-1.0.0.jar s3://hello-lambda-5318

aws lambda create-function --function-name hello-function-001 --role arn:aws:iam::006225811947:role/hello-lambda-role --runtime java11 --handler com.amazonaws.lambda.demo.HelloLambda::handleRequest --code S3Bucket=hello-lambda-5318,S3Key=demo-1.0.0.jar

aws lambda update-function-code --function-name hello-lambda-function \
 --s3-bucket hello-lambda-5318 --s3-key demo-1.0.0.jar

aws lambda create-function --function-name hello-function --role arn:aws:iam::006225811947:role/hello-lambda-role --runtime java11 --handler com.amazon.test.App::handleRequest --code S3Bucket=hello-lambda-8376,S3Key=hello-lambda.jar
```
