# aws-cloud-formation-create-server
```
aws cloudformation package \
    --template-file app/environment.yaml  \
    --s3-bucket cf-templates-abcdefgs-us-west-2 \
    --output-template-file /tmp/packaged.yaml --profile jollycoding \
&& aws cloudformation deploy \
    --template-file /tmp/packaged.yaml \
    --stack-name dev-env \
    --capabilities CAPABILITY_NAMED_IAM \
    --parameter-overrides "EC2KeyPair=jollycoding-test" "EnvironmentName=dev" "EnvironmentType=nonprod"
```