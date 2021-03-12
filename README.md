# AWS-SDK-2-DEBUG-2325


Repo to debug AWS Java SDK 2.0 issue #2325
## Usage
`./gradlew run --args="{TARGET_BUCKET} java-sample-upload"` makes a URL to upload `java-sample-upload` to the `{TARGET_BUCKET}` bucket.


## Credentials
The code uses the default credential provider, so your loaded AWS session is reused. If you want to emulate K8S, you need to steal the token.

This gives you the environment variables you need to set, as well as a token path in `AWS_WEB_IDENTITY_TOKEN_FILE`. Copy that file to your machine and reexport all variables, e.g.
```
export AWS_WEB_IDENTITY_TOKEN_FILE=$(pwd)/token
export AWS_ROLE_ARN=arn:aws:iam::..........
export AWS_REGION=eu-west-1
```
You can use `aws sts get-caller-identity` to verify that you did it correctly.
