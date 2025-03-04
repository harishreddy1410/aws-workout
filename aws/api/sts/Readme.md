## Cretae a new user
```sh
aws iam create-user --user-name sts-machine-user
aws iam create-access-key --user-name sts-machine-user --output table
```

Then use the "aws configure --profile=dev" to configure the profile in local environment
Verify using aws cli command 
```sh
aws sts get-caller-identity
```

Make sure you dont have access aws resource like S3 
```sh
aws s3 ls --profile dev
``` 
> An error occurred (AccessDenied) when calling the ListBuckets operation: Access Denied



## Create a Role 
Create a role that will access a new resource
Make sure you can execute the bash script
```sh
chmod u+x bin/deploy
./bin/deploy
```

## Use new user credentials and assume a role

```sh
aws iam put-user-policy \
    --user-name sts-machine-user \
    --policy-name StsAssumePolicy \
    --policy-document file://policy.json
```

```sh
aws sts assume-role \
    --role-arn arn:aws:iam::123098983:role/stsrole \
    --role-session-name s3-access-example \
    --profile dev
```

# Cleanup
Tear down your cloudformation stack via the AWS Management console 

```sh
aws iam delete-user-policy --user-name sts-machine-user --policy-name StsAssumePolicy
aws iam delete-access-key --access-key-id AKIAHJGJHGJHGJH --user-name sts-machine-user
aws iam delete-user --user-name sts-machine-user
```