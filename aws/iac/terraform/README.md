https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli
https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket

1. create the folder terrform in repo 
2. cd aws/iac/terraform
3. terraform init
4. terraform plan #this will show the changes making)
5. terraform apply
6. terraform destroy
7. aws s3 cp s3://terraform-20250127044737264500000001/file.txt - && cat - # To read the file and uploaded to s3 
Make changes to the txt.file
8. added the line  etag = filemd5("file.txt"), it will make terraform to detect the changes to the content of file
9. terraform plan
10. terraform apply 
11. aws s3 cp s3://terraform-20250127044737264500000001/file.txt - && cat 
12. This will show the updated changes

