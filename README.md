# aws-sam-fastapi-example-quickstart

This little project contains the source code for a serverless application that you are able to deploy with AWS SAM CLI. It is the example used by FastAPI, but slightly reworked in order for it to be deployable via AWS SAM. It contains the following folders and files:

- example - Python 3.x code for the application's Lambda function. It's basically a FastAPI app, with a mangum wrapper.
- template.yaml - The template for AWS SAM that defines the application's AWS resources. There is no included security so if deployed, your API will be public.

## Deploying

[Install the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

Then:

```bash
sam build
sam deploy --guided
```
