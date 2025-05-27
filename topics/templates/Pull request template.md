## Link to parent 🔗

- https://test.atlassian.net/browse/TEST-61

## Link to code-review ticket 🔗

- https://test.atlassian.net/browse/TEST-64

# Pull request template

## Pull-request link 👨‍💻

- [Pull-request link](https://eu-west-1.console.aws.amazon.com/codesuite/codecommit/repositories/test-services/pull-requests/1935/details?region=eu-west-1)

## Build 🏭

- [AWS CodeBuild Link](https://eu-west-1.console.aws.amazon.com/codesuite/codebuild/518241560725/projects/test-services-build/history?region=eu-west-1&builds-meta=eyJmIjp7InRleHQiOiIifSwicyI6e30sIm4iOjIwLCJpIjowfQ)

## SonarQube ☕

- [SonarQube Link](https://sonar.devops..cloud/dashboard?id=test-services&pullRequest=1899)

## CodePipeline 🚀

- [Pipeline Link (`DevOps` account)](https://eu-west-1.console.aws.amazon.com/codesuite/codepipeline/pipelines/test-services-development/view?region=eu-west-1)

## Description 📚

This pull-request introduces AWS Textract as OCR processor in the IDP Services Project.

## Type of change ✨

### Textract integration ✨

Change is introduced mainly through the classes
in `text-recognition/src/main/java/cloud/test/idp/services/recognition/text/engine/textract`. Example:

![[ARGEN003-61-textract_file_structure.png]]

Also overall refactoring has been
performed for the `recognition` project including removing warnings, fixing naming conventions, Sonarlint
etc.

#### Uploading files to S3 Bucket 🧺

Happens in the `text-recognition/src/main/java/cloud/test/idp/services/recognition/text/engine/textract/main/AmazonFileHandler.java`

the handler is called afterwards in `AmazonTextractRecognition` to upload the file, get the OcrResult and then delete it from S3:

```Java
@Override
public OcrResult extractText(File file, List<String> featureTypes, ContentType contentType)
        throws IOException, TextRecognitionException {
    fileHandler.uploadFile(file);
    OcrResult ocrResult = getOcrResult(file, featureTypes, contentType);
    fileHandler.deleteFile(file);
    return ocrResult;
}
```

### Integration in CDK 🚀

Check the classes in `test-cdk/src/main/java/cloud/test/idp/services/deploy/recognition/text`

## How to test? ✅

### Test configuration 🔧

In order to run the tests you need Docker running.
Make sure you fill in the following values in `text-recognition/src/test/resources/application.properties`:

```properties
engine.textract.access_key=ACCESS_KEY
engine.textract.secret_key=SECRET_KEY
engine.textract.session_token=SESSION_TOKEN
engine.textract.bucket=textract-console-eu-west-1-0f24fae2-3d72-4030-8d8c-7c7560d41708
engine.textract.region=eu-west-1
engine.textract.role.arn=ENGINE_TEXTRACT_ROLE_ARN
engine.textract.sqs.queue.url=ENGINE_TEXTRACT_SQS_QUEUE_URL
engine.textract.sns.topic.arn=ENGINE_TEXTRACT_SNS_TOPIC_ARN
```

where `ACCESS_KEY`, `SECRET_KEY` and `SESSION_TOKEN` can be taken from your AWS Sandbox account, clicking on Access
keys:

and `ENGINE_TEXTRACT_ROLE_ARN`, `ENGINE_TEXTRACT_SQS_QUEUE_URL`, `ENGINE_TEXTRACT_SNS_TOPIC_ARN` can be fetched from the [IAM Roles](https://us-east-1.console.aws.amazon.com/iam/home?region=eu-west-1#/roles), [SQS Queue Service](https://eu-west-1.console.aws.amazon.com/sqs/v3/home?region=eu-west-1)

The test uploads a file to the S3 bucket, then does the extraction and deletes the file afterwards. Files are read from `text-recognition/src/test/resources`.

### Run tests 🧪

Run functions in `src/test/java/cloud/test/idp/services/recognition/text/AmazonTextractRecognitionTest.java` and

`text-recognition/src/test/java/cloud/test/idp/services/recognition/text/AmazonFileHandlerTest.java`

Keep in mind, that for freshly uploaded files, getting the `OcrResult` from the queue takes up to two minutes per file, which might case issues:


### Possible problems during testing 🐛

When running tests, if you see following problem:

```java
software.amazon.awssdk.services.sns.model.SnsException: The security token included in the request is invalid (Service: Sns, Status Code: 403, Request ID: 1a420e26-b7dd-5ba6-a17a-50e92e2b635d)
```

I had the same error, even after re-running `aws configure`, and inputting a new `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`.

What fixed it for me was to delete my `~/.aws/credentials` file and re-run `aws configure`.

It seems that my `~/.aws/credentials` file had an additional value: `aws_session_token` which was causing the error. After deleting and re-creating the `~/.aws/configure` using the command `aws configure`, there is now only values for `aws_access_key_id` and `aws_secret_access_key`.
