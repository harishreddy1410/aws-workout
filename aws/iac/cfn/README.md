1. Create a Template yaml file 
    To validate the file run command "aws cloudformation validate-template --template-body file://templa
    te.yaml"
    aws cloudformation describe-stack-events --stack-name cfn-s3-sample

    aws cloudformation execute-change-set --stack-name cfn-s3-sample --change-set-name awscli-cloudformation-package-deploy-1737440896

    aws cloudformation delete-stack --stack-name cfn-s3-sample
    
2. Create a Bash file 
3. chmod u+x aws/iac/cfn/deploy
4. cd aws/iac/cfn/
5. ls
6. run "./deploy"