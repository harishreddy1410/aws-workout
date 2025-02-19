# Create a S3 bucket 
```
aws s3 mb s3:\\my-s3bucket-123
```
# Create a new file 
echo "Hello world" > hello.txt

# Upload file with metadata

aws s3api put-object --bucket my-s3bucket-123 --key hello.txt --body hello.txt --metadata Name=Harish

# Get Metadata through the head object 

aws s3api  head-object --bucket my-s3bucket-123 --key hello.txt

# Cleanup 
aws s3 rm s3:\\my-s3bucket-123\hello.txt
aws s3 rb s3:\\my-s3bucket-123