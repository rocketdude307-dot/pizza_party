# Pizza Party Serverless CloudFormation/SAM Template

Deploy `pizza-party-serverless.yaml` with AWS SAM.

## Why this version fixes your build issue
- Uses `python3.11` instead of `python3.12`, which is more commonly available on local SAM setups.
- Uses valid SAM `InlineCode` for Lambda (instead of `CodeUri` + `ZipFile`, which is invalid for SAM functions).
- Replaces unsupported `AWS::S3::Object` with a custom resource writer Lambda that uploads `index.html` during deployment.

## Features
- User parameter for app name: `PizzaPartyAppName`
- RSVP + pizza/toppings voting APIs
- DynamoDB-backed storage for votes/results
- Dashboard tally with Chart.js visualizations and pizza image banner
- Slices-per-person input and computed pizza order recommendations
- Optional Bedrock AI suggestions endpoint

## Build & Deploy
```bash
sam build -t pizza-party-serverless.yaml
sam deploy --guided
```
