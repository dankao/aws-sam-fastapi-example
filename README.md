# aws-sam-fastapi-example-quickstart

This little project contains the source code for a serverless application that you are able to deploy with AWS SAM CLI. It is the example used by FastAPI, but slightly reworked in order for it to be deployable via AWS SAM. It contains the following folders and files:

- example - Python 3.9 (Latest version available on Amazon Lambda, still? Come'mon Amazon...) code for the application's Lambda function. It's basically a FastAPI app, with a mangum wrapper.
- template.yaml - The template for AWS SAM that defines the application's AWS resources. There is no included security so if deployed, your API will be public.

## Deploying

[Install the AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

Then:

```bash
sam build
sam deploy --guided
```

At the end of a successful deploy, you should get something similar to this:

```bash
-----------------------------------------------------------------------------
Outputs
-----------------------------------------------------------------------------
Key                 ApiUrl
Description         URL of your API
Value               https://xxxxxxxxxx.execute-api.us-east-1.amazonaws.com/
-----------------------------------------------------------------------------
```

That is the URL of your endpoint. If you access the endpoint with your browser, it should respond with the automatic interactive API documentation provided by Swagger UI.

```bash
{"Hello":"World"}
```

If you access the URL with `/docs`, it should display the automatic API documenation provided by Swagger UI.

## Deleting

To delete what you just created, just type:

```bash
sam delete --stack-name aws-sam-fastapi-example
```

It will delete your AWS Lambda fuction, AWS API Endpoints, AWS S3 objects (artifacts) and AWS CloudFormation stack related to the application.
