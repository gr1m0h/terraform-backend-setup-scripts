# terraform-backend-setup-scripts
## Usage
1. Run init.sh

	```sh
	bash init.sh <STACK_NAME> <S3_BUCKET_NAME> <DYNAMODB_TABLE_NAME>
	```

1. terraform init

	```sh
	terraform init \
		-backend-config="bucket=<S3_BUCKET_NAME>" \
		-backend-config="dynamodb_table=<DYNAMODB_TABLE_NAME>"
	```

### When removing the Terraform backend

```sh
aws cloudformation delete-stack --stack-name <STACK_NAME>
```
